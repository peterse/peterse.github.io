general notes
 - an overall goal would be to predict scites as a function of title and author list and maybe abstract (eww)
 - main problem is that median scites are nonstationary, so we could predict a multiplication factor over the median/mean number of scites of a paper in a given time
 - the author(s) are categorical; maybe a one-hot vector for a particular author and a list of authors is a sum of such vectors...?
 - 
 - to make this work, we could normalize total scites by the number of "active scitors", which could be something like the number of unique scitors over the last 2 weeks