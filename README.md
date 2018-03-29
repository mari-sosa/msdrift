# README #

This is a franklab fork of the magland msdrift repository from github.

It contains all source code for drift tracking as well as the updated pyms.anneal_segments to anneal clusters across all segments.

**How to use:**\
We can pull updates from the magland repo using:
> git pull upstream master

Franklab-specific changes will only get pushed to Mari's github fork and this bitbucket repo.

**How this is different than the magland repo:**\
The updated version of p_anneal_segments.py has the following modifications:

  Major:\ 
	  * Loops through all combinations of segments to compute distances between clusters and anneal nearest pairs, as opposed to annealing only over neighboring segments. This means that even if a given cluster is absent for some segments, it will be annealed over all segments for which it is present.
  Minor:\ 
      * Bug fixes to avoid crashes when a segment is empty of any clusters (if curation has already happened).\
      * Uses first and last 500 events of each cluster for template matching.\
      * Uses clip_size=50.\
      * Empty segments are reported to the console and skipped.\
      * Cluster numbers, time offests, and annealing progress are reported to the console.\

