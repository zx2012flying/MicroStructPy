.. _ex_colormap:

========
Colormap
========

In this example, a 3D microstructure is generated with grains colored by their
seed number, rather than the material.

XML Input File
==============

The basename for this input file is ``colormap.xml``.
The file can be run using this command::

    microstructpy --demo=colormap.xml

The full text of the script is:

.. literalinclude:: ../../../../examples/colormap.xml
    :language: xml


Materials
=========

There is a single material with grain sizes ranging from 1 to 3 on a
uniform distribution.

Domain
======

The domain of the microstructure is a :class:`.Cube`.
The cube's center is at the origin and its side length is 15.

Settings
========

The output directory is ``./colormap``, which contains the text files
and PNG plots of the microstructure.
The minimum dihedral angle for the mesh elements is set to 15 degrees to
ensure mesh quality.

The ``<color_by>`` option indicates how to color seeds in the output plots.
There are three values available for this option: "material", "seed number",
and "material number".
The "material" value will use colors specified in each ``<material>`` field.
The "seed number" value will use the seed numbers as values for a colormap.
Similarly, "material number" will use the material number in a colormap.

The ``<colormap>`` option indicates which colormap should be used in the output
plot.
The default colormap is "viridis", which is also the default for matplotlib.
A complete listing of available colormaps is available on the matplotlib
`Choosing Colormaps in Matplotlib`_ webpage.

Output Files
============

.. only:: not latex

    The three plots that this file generates are the seeding, the polygon mesh,
    and the triangular mesh.
    These three plots are shown below.

    .. figure:: ../../../../examples/colormap/seeds.png
        :alt: Seed geometries.

        Seed geometries
        
    .. figure:: ../../../../examples/colormap/polymesh.png
        :alt: Polygonal mesh.

        Polygonal mesh
        
    .. figure:: ../../../../examples/colormap/trimesh.png
        :alt: Triangular mesh.

        Triangular mesh

.. only:: latex

    .. raw:: latex

        The three plots that this file generates are the seeding, the polygon mesh,
        and the triangular mesh.
        These three plots are shown in Fig.~\ref{fig:ex_colormap}.

        \begin{figure}[htbp]
            \centering
            \subfloat[Seed geometries]{
                \includegraphics[width=0.3\textwidth]{../../examples/colormap/seeds.png}
            }
            ~
            \subfloat[Polygonal mesh]{
                \includegraphics[width=0.3\textwidth]{../../examples/colormap/polymesh.png}
            }
            ~
            \subfloat[Triangular mesh]{
                \includegraphics[width=0.3\textwidth]{../../examples/colormap/trimesh.png}
            }
            \caption{Output plots for colormap example.}
            \label{fig:ex_colormap}
        \end{figure}


.. _`Choosing Colormaps in Matplotlib`: https://matplotlib.org/3.1.0/tutorials/colors/colormaps.html