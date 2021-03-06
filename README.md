#
# CDDL HEADER START
#
# The contents of this file are subject to the terms
# of the Common Development and Distribution License
# (the "License").  You may not use this file except
# in compliance with the License.
#
# You can obtain a copy of the license at
# src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing
# permissions and limitations under the License.
#
# When distributing Covered Code, include this CDDL
# HEADER in each file and include the License file at
# usr/src/OPENSOLARIS.LICENSE.  If applicable,
# add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your
# own identifying information: Portions Copyright [yyyy]
# [name of copyright owner]
#
# CDDL HEADER END
#

#
# Copyright 2005 Sun Microsystems, Inc.  All rights reserved.
# Use is subject to license terms.
#

Building the tarball
--------------------
As long as cc is in your path, (gcc on Linux),

% tar xf libMicro.tar
% make

will build the benchmark suite.

Running the benchmarks
-----------------------

A set of generic scripts to invoke each micro benchmark
are created in the bin directory; these may be invoked
directly.  Note that the actual binaries are created in
OS-specific directories; this allows one to build for
all varients (x86/sparc/Solaris/Linux) in one place.

To collect a complete set of benchmarks, use the bench
script and redirect its output to a file.

% ./bench > output

To compare the output of two or more runs, use multiview in the src
directory:

% ./multiview reference compare1 compare2 compare2 > compare.html
%

where the reference and compare files contain the output of different
libmicro runs.

The compare.html file will allow quick comparisons to be drawn,
allowing a variety of experiments to be quickly analyzed.

All benchmarks support the following options:

       [-1] (single process; overrides -P > 1)
       [-A] (align with clock)
       [-B batch-size (default 10)]
       [-C minimum number of samples (default 0)]
       [-D duration in msecs (default 10s)]
       [-E (echo name to stderr)]
       [-H] (suppress headers)
       [-I] specify approx. time per op in nsecs
       [-L] (print argument line)
       [-M] (reports mean rather than median)
       [-N test-name ]
       [-P processes (default 1)]
       [-S] (print detailed stats)
       [-T threads (default 1)]
       [-V] (print the libMicro version and exit)
       [-W] (flag possible benchmark problems)

