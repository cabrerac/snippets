\ifndef{deepMotorcycle}
\define{deepMotorcycle}
\editme

\include{_gp/includes/motorcycle-helmet-gp.md}
\include{_deepgp/includes/deepgp-enhance.md}

\setupcode{import deepgp}
\code{layers = [y.shape[1], 1, x.shape[1]]
inits = ['PCA']*(len(layers)-1)
kernels = []
for i in layers[1:]:
    kernels += [GPy.kern.RBF(i)]
m = deepgp.DeepGP(layers,Y=yhat, X=x, 
                  inits=inits, 
                  kernels=kernels, # the kernels for each layer
                  num_inducing=20, back_constraint=False)



m.initialize()}

\code{m.staged_optimize(iters=(1000,1000,10000), messages=(True, True, True))}

\setupdisplaycode{import teaching_plots as plot
import mlai}
\displaycode{fig, ax=plt.subplots(figsize=plot.big_wide_figsize)
plot.model_output(m, scale=scale, offset=offset, ax=ax, xlabel='time', ylabel='acceleration/$g$', fontsize=20, portion=0.5)
ax.set_ylim(ylim)
ax.set_xlim(xlim)
mlai.write_figure(filename='../slides/diagrams/deepgp/motorcycle-helmet-deep-gp.svg', 
            transparent=True, frameon=True)}

\subsection{Motorcycle Helmet Data Deep GP}

\includediagram{../slides/diagrams/deepgp/motorcycle-helmet-deep-gp}

\setupdisplaycode{import teaching_plots as plot
import mlai}
\displaycode{fig, ax=plt.subplots(figsize=plot.big_wide_figsize)
plot.model_sample(m, scale=scale, offset=offset, samps=10, ax=ax, xlabel='time', ylabel='acceleration/$g$', portion = 0.5)
ax.set_ylim(ylim)
ax.set_xlim(xlim)

mlai.write_figure(figure=fig, filename='../slides/diagrams/deepgp/motorcycle-helmet-deep-gp-samples.svg', 
                  transparent=True, frameon=True)}

\subsection{Motorcycle Helmet Data Deep GP}

\includediagram{../slides/diagrams/deepgp/motorcycle-helmet-deep-gp-samples}

\displaycode{m.visualize(xlim=xlim, ylim=ylim, scale=scale,offset=offset, 
            xlabel="time", ylabel="acceleration/$g$", portion=0.5,
            dataset='motorcycle-helmet',
            diagrams='../slides/diagrams/deepgp')}

\subsection{Motorcycle Helmet Data Latent 1}

\includediagram{../slides/diagrams/deepgp/motorcycle-helmet-deep-gp-layer-0}

\subsection{Motorcycle Helmet Data Latent 2}

\includediagram{../slides/diagrams/deepgp/motorcycle-helmet-deep-gp-layer-1}

\displaycode{fig, ax=plt.subplots(figsize=plot.big_wide_figsize)
m.visualize_pinball(ax=ax, xlabel='time', ylabel='acceleration/g', 
                    points=50, scale=scale, offset=offset, portion=0.1)
mlai.write_figure(figure=fig, filename='../slides/diagrams/deepgp/motorcycle-helmet-deep-gp-pinball.svg', 
                  transparent=True, frameon=True)}

\subsection{Motorcycle Helmet Pinball Plot}

\includediagram{../slides/diagrams/deepgp/motorcycle-helmet-deep-gp-pinball}
\endif
