tsx-lexer
=========

A TSX lexer for Pygments

Usage with Sphinx
-----------------

To use within Sphinx, simply specify ``tsx`` for your ``code-block``::

    .. code-block:: tsx

        const BlogTitle = ({ children }) => (
          <h3>{children}</h3>
        );
        // class component
        class BlogPost extends React.Component {
          renderTitle(title) {
            return <BlogTitle>{title}</BlogTitle>
          };
          render() {
            return (
            <div className="blog-body">
              {this.renderTitle(this.props.title)}
              <p>{this.props.body}</p>
            </div>
            );
          }
        }

Usage with mkdocs
-----------------

First, you need to create the ``CSS`` for the highlighting:

.. code-block:: bash

  $ pygmentize -S default -f html -a .codehilite > code/pygments.css

Then, add the following to your ``mkdocs.yml``:

.. code-block:: yaml

  markdown_extensions:
    - codehilite
  extra_css: [pygments.css]

Now, you can use ``tsx`` in your code blocks::

    ```tsx
    const BlogTitle = ({ children }) => (
      <h3>{children}</h3>
    );
    // class component
    class BlogPost extends React.Component {
      renderTitle(title) {
        return <BlogTitle>{title}</BlogTitle>
      };
      render() {
        return (
        <div className="blog-body">
          {this.renderTitle(this.props.title)}
          <p>{this.props.body}</p>
        </div>
        );
      }
    }
    ```
