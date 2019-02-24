\ifndef{embodimentFactorsShort}
\define{embodimentFactorsShort}
\editme

\notes{\subsection{Natural and Artificial Intelligence: Embodiment Factors}}

\newslide{"Embodiment Factors"}

\table{
<table>
 <tr>
  <td></td>
  <td align="center">\includejpg{../slides/diagrams/IBM_Blue_Gene_P_supercomputer}{40%}</td>
  <td align="center">\includejpg{../slides/diagrams/ClaudeShannon_MFO3807}{25%}{}</td>
 </tr>
 <tr>
  <td>compute</td>
  <td align="center">$$\approx 100 \text{ gigaflops}$$</td><td align="center">$$\approx 16 \text{ petaflops}$$</td>
 </tr>
 <tr>
  <td>communicate</td>
  <td align="center">$$1 \text{ gigbit/s}$$</td>
  <td align="center">$$100 \text{ bit/s}$$</td>
 </tr>
 <tr>
  <td>(compute/communicate)</td>
  <td align="center">$$10^{4}$$</td>
  <td align="center">$$10^{14}$$</td>
 </tr>
</table>}{}{embodiment-factors}

\slides{See \href{https://arxiv.org/abs/1705.07996}{"Living Together: Mind and Machine Intelligence" @Lawrence:embodiment17}}

\notes{There is a fundamental limit placed on our intelligence based on our ability to communicate. Claude Shannon founded the field of information theory. The clever part of this theory is it allows us to separate our measurement of information from what the information pertains to[^knowledge-representation].

[^knowledge-representation]: the challenge of understanding what information pertains to is known as knowledge representation. 

Shannon measured information in bits. One bit of information is the amount of information I pass to you when I give you the result of a coin toss. Shannon was also interested in the amount of information in the English language. He estimated that on average a word in the English language contains 12 bits of information. 

Given typical speaking rates, that gives us an estimate of our ability to communicate of around 100 bits per second [@Reed-information98]. Computers on the other hand can communicate much more rapidly. Current wired network speeds are around a billion bits per second, ten million times faster. 

When it comes to compute though, our best estimates indicate our computers are slower. A typical modern computer can process make around 100 billion floating point operations per second, each floating point operation involves a 64 bit number. So the computer is processing around 6,400 billion bits per second. 

It's difficult to get similar estimates for humans, but by some estimates the amount of compute we would require to *simulate* a human brain is equivalent to that in the UK's fastest computer [@Ananthanarayanan-cat09], the MET office machine in Exeter, which in 2018 ranks as the 11th fastest computer in the world. That machine simulates the world's weather each morning, and then simulates the world's climate in the afternoon. It is a 16 petaflop machine, processing around 1,000 *trillion* bits per second.}


\endif
