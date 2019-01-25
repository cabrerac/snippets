\ifndef{dellaGattaGeneData}
\subsection{Della Gatta Gene Data}

* Given given expression levels in the form of a time series from @DellaGatta:direct08. 

\setupcode{import numpy as np
import pods}

\code{data = pods.datasets.della_gatta_TRP63_gene_expression(data_set='della_gatta',gene_number=937)

x = data['X']
y = data['Y']

offset = y.mean()
scale = np.sqrt(y.var())}

\setupdisplaycode{import matplotlib.pyplot as plt
import teaching_plots as plot
import mlai}

\displaycode{
xlim = (-20,260)
ylim = (5, 7.5)
yhat = (y-offset)/scale

fig, ax = plt.subplots(figsize=plot.big_wide_figsize)
_ = ax.plot(x, y, 'r.',markersize=10)
ax.set_xlabel('time/min', fontsize=20)
ax.set_ylabel('expression', fontsize=20)
ax.set_xlim(xlim)
ax.set_ylim(ylim)

mlai.write_figure(figure=fig, 
                  filename='../slides/diagrams/datasets/della-gatta-gene.svg', 
				  transparent=True, 
				  frameon=True)}

\newslide{Della Gatta Gene Data}

\div{\includediagram{../slides/diagrams/datasets/della-gatta-gene}}{}{text-align:center}

\notes{}

\define{dellaGattaGeneData}
\endif
