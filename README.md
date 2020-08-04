# docs
# Writing and publishing blog posts on the OpenLiberty.io blog

* [Authors: creating a new blog post](#Authors-creating-a-new-blog-post)
* [Editors: editing and publishing a post](#Editors-editing-and-publishing-a-post)
* [Authors and Editors: updating a published post](#Authors-and-Editors-updating-a-published-post)
* [Troubleshooting Asciidoc](#Troubleshooting-Asciidoc)
* [Running a Docker container for local preview](#Running-a-Docker-container-for-local-preview)


## Authors: creating a new doc

These steps are to be completed by the author of the doc:
  

1. Clone [the docs repo](https://github.com/OpenLiberty/docs) and create your feature branch off of the default `vNext` branch. Include the number of the Git issue for the doc in the name of your branch (e.g. `1234-concept-topic`). Do _all_ your writing and editing in this branch.

2. Create your doc using [Asciidoc](https://asciidoctor.org/docs/asciidoc-syntax-quick-reference/) markup (use an editor such as [Atom](https://atom.io/) or [VSCode with the Asciidoc plugin](https://marketplace.visualstudio.com/items?itemName=joaompinto.asciidoctor-vscode)).

3. When you have finished the post, check that it renders correctly by using the preview function in your editor. Make sure to run [Acrolinx](https://www.acrolinx.com/) to check for grammar and IBM style issues. 

4. Push the file to GitHub, then create a pull request (PR) into the `draft` branch.

   Link the PR to the issue you created in Step 1.

5. Request a build of the [draft openliberty.io site](https://draft-openlibertyio.mybluemix.net/docs/):
    1. Sign in to [Travis CI](https://travis-ci.com/github/OpenLiberty/openliberty.io) with your GitHub account.
    2. Click **More Options > Trigger Build**. Make sure the `master` branch is selected, then click **Trigger custom build**.
    
          The draft site build starts running.

6. When the build is finished, check that the doc renders correctly on the [draft site](https://draft-openlibertyio.mybluemix.net/docs/). Post a link to your draft in the Git issue for the doc.

  If you see any problems (e.g. formatting or typos), resolve them first in your branch, create another PR into `draft` branch (link the PR to the issue again), then run the [draft site build from Travis CI](https://travis-ci.com/github/OpenLiberty/openliberty.io) again.

7. Submit your doc for technical, strategist, peer, and editorial reviews. 

  Reviewers should leave comments in the git issue for the doc. Make sure to respond to their comments in the issue and document hwo the concerns that they raised have been addressed. When the reviewer is satisfied with the draft, they can sign off by adding the appropriate label to the Git issue:`technical reviewed`, `peer reviewed`, `strategist reviewed`, or `editorial reviewed`. Make sure to keep the Git "Pipelines" status updated in the issue to reflect the stage of review that the doc is ready for or undergoing.

  If the doc is a task, it must be tested so that the steps are verified. Coordinate the testing with the technical reviewer and add the `doc tested` label when the steps have been verified.

8. When all the reviews are complete, if your doc is targeted to publish in the next release, create a PR from your branch (_not_ from the `draft` branch) to the `staging` branch. Do not create the PR to staging until the week before the release in which your doc is targeted to publish. If your doc is not targeted to publish until a later release, do not make the PR to staging.

  Link the PR to the issue. Request a review of the PR from David Mueller (`dmuelle`) or Charlotte Holt (`Charlotte-Holt`).

  In the PR, provide a link to your post on the [draft site](https://draft-openlibertyio.mybluemix.net/blog/).
   
9. If any changes are requested to the PR, make them in your branch, push the changes to the draft branch, then run the draft site build from Travis CI again to check that they are fine on the draft site.

  This automatically updates the PR to staging.

10. Once the PR to staging is approved and merged, request a build of the [staging openliberty.io site from Travis CI](https://travis-ci.com/github/OpenLiberty/openliberty.io). To trigger a staging build, use the same procedure that you used in step 5 to trigger a draft build.

11. When the build finishes, check to make sure the doc renders correctly on the [staging site](https://staging-openlibertyio.mybluemix.net/blog/). If any changes are needed make sure to add them to the draft branch and review on the draft site before making a PR to staging.

12. Once you verify the doc, post a link to it on the staging site to the Git issue and change the issue status to `Ready to publish`. The ID focals will merge the staging draft to `vNext` so that it publishes with the next release.



