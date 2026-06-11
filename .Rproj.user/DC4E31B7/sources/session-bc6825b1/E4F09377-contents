\name{rsvmf}
\alias{rsvmf}
\title{
Random value simulation from the scaled von Mises--Fisher distribution
}

\description{
Random value simulation from the scaled von Mises--Fisher distribution.
}

\usage{
rsvmf(n, mu, a, kappa, Gamma)
}

\arguments{
\item{n}{
The sample size.
}
\item{mu}{
The mean direction.
}
\item{a}{
The vector of alphas.
}
\item{kappa}{
The concentration parameter.
}
\item{Gamma}{
The matrix with the \eqn{\gm{\gamma}} vectors.
}
}

\value{
A matrix with the simulated data.
}

\references{
Scealy J.L. and Wood A.T.A. (2019). Scaled von Mises-Fisher distributions and regression models for paleomagnetic directional data.
Journal of the American Statistical Association, 114(528):  1547--1560.
}

\author{
Michail Tsagris.

R implementation and documentation: Michail Tsagris \email{mtsagris@uoc.gr}.
}

%\note{
%%  ~~further notes~~
%}

\seealso{
\code{\link{svmf.mle}
}
}

\examples{
mu <- rnorm(3)
mu <- mu / sqrt( sum(mu^2) )
a <- c(1, 3, 1/3)
y <- rsvmf(1000, mu, a, 20)
svmf.mle(y)
}
