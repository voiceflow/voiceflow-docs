---
title: Document Chunk Retrieval
excerpt: Retrieves the chunks for a Knowledge Base doc by documentID.
api:
  file: knowledge-base-management-apis.json
  operationId: get_v3alpha-knowledge-base-docs-documentid
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Request Fields

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Property
      </th>

      <th style={{ textAlign: "left" }}>
        Description & Example
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        **documentID**
        (path variable)
      </td>

      <td style={{ textAlign: "left" }}>
        A unique identifier of the document object (a string).\
        To get the list of documentID's, use the **GET Document List** Knowledge Base API.
      </td>
    </tr>
  </tbody>
</Table>

## Sample Response

```json JSON
{
	"data": {
		"documentID": "6515dccab4bc5400060fbc6a",
		"data": {
			"type": "url",
			"name": "familyhandyman.com/article/simple-step-stool/",
			"url": "https://www.familyhandyman.com/article/simple-step-stool/"
		},
		"updatedAt": "2023-09-28T20:06:34.049Z",
		"status": {
			"type": "SUCCESS"
		},
		"tags": [
			"beginner",
			"small_scale"
		]
	},
	"chunks": [
		{
			"chunkID": "868a0cdc-5e3a-11ee-ae78-de8d0308bfff",
			"content": "Simple Step Stool | Family Handyman Skip to main content Watch Free Pro New Homeowners Projects DIY University Shopping Subscribe Best Hot Tubs Home  Skills  Woodworking Simple Step Stool Andrew ZoellnerUpdated: Feb. 25, 2022"
		},
		{
			"chunkID": "868a0f34-5e3a-11ee-ae78-de8d0308bfff",
			"content": "This DIY step stool is an easy woodworking project which takes minimal effort to create a beautiful piece. Family Handyman"
		},
		{
			"chunkID": "868a1010-5e3a-11ee-ae78-de8d0308bfff",
			"content": "Here’s a great gift idea that will draw raves. The joints are accurately made in seconds with a plate jointer, but don’t tell your admirers. You’ll also need a power saw to crosscut the boards and a jigsaw to cut the half-circles in the risers. The lumber you’ll need:"
		},
		{
			"chunkID": "868a10ce-5e3a-11ee-ae78-de8d0308bfff",
			"content": "One 8-ft. 1×8 clear hardwood board (actual width is 7-1/4 in. and actual thickness is 3/4 in.). Oak is a good choice because it’s readily available at home centers. One 4-ft. 1×3 hardwood board (actual width is 2-1/2 in. and actual thickness is 3/4 in.). Cut the 8-ft. board into: Two 22-in. riser boards Two 11-in. riser boards One 14-in. step board One 14-in. seat board"
		},
		{
			"chunkID": "868a116e-5e3a-11ee-ae78-de8d0308bfff",
			"content": "You’ll use 94 in. of the 96-in. board, so make practice cuts on a scrap board first to check the angle and length of cut. Don’t cut the 3-ft. 1×3 board until you’ve dry-assembled the step, seat and risers and measured for a perfect fit."
		},
		{
			"chunkID": "868a1218-5e3a-11ee-ae78-de8d0308bfff",
			"content": "To create two risers, join the 11-in. boards to the 22-in. boards with No. 20 biscuits and glue. Let dry 30 minutes, then lay the step and seat across and mark for two No. 20 biscuits at each joint. Dry-assemble the step, seat and risers with biscuits, then cut and snugly fit the crosspieces. Mark the riser-to-crosspiece joint and cut slots for No. 0 biscuits. Glue and firmly clamp the step, seat and crosspieces to the risers. Check for square and let dry 30 minutes, then cut out the 4-1/2 in. diameter arc on the bottom of the risers to create the legs. Finish-sand and apply your favorite finish. This project is designed for use on hard-surface flooring only – not carpeting. We’ve got plans for lots of different simple stools, like this one that you make using your jigsaw. Originally Published: November 15, 2017 Now Trending Should I Inspect My Fire Extinguisher? Beginner’s Guide To Reupholstering Furniture 9 Clever IKEA Billy Bookcase Hacks About Us Magazine Skills Pro House Outdoors Trends Our Brands Reader’s Digest Taste of Home Birds & Blooms The Healthy Subscribe Give a Gift Advertise with Us Customer Care Content Submission Contact Us Privacy Policy Your CA Privacy Rights Do not Sell or Share My Personal Information Terms of Use Accessibility Statement About Ads Affiliate Program Cookie Settings License our Content © 2023 Home Service Publications, Inc. Sign Up For Our Newsletter Enter email address Sign Up Do it right, do it yourself! Search terms"
		},
		{
			"chunkID": "868a12c2-5e3a-11ee-ae78-de8d0308bfff",
			"content": "We are no longer supporting IE (Internet Explorer) as we strive to provide site experiences for browsers that support new web standards and security practices. We recommend our users to update the browser. Google Chrome Apple Safari Mozilla Firefox Microsoft Edge DIY Skills & TechniquesMore Items Carpentry Concreting Drywalling Electrical Flooring Landscaping Masonry Painting Plumbing Roofing Tiling Woodworking ProMore Items Gear & Apparel Industry News Pro Tips Stuff We Love Tools & Equipment Trades ALL PRO Garage & WorkshopMore Items Automotive Garage Power Equipment Tools & Supplies Utility Trailers Woodworking Home InspirationMore Items Cleaning Decor Energy Saving Pets Safety Saving Money Storage & Organization HouseMore Items Appliances Fixtures Parts of House Rooms Systems ALL HOUSE OutdoorsMore Items Camping Deck & Patio Garden Grilling Landscaping Lawn Shed Yard & Garden Structures ALL OUTDOORS Pest ControlMore Items Ants Cockroaches Flies Mice Spiders Stinging Pests ALL PEST CONTROL ProductsMore Items Stuff We Love ALL PRODUCTS Technology & InnovationMore Items Home Security Smart Home Videos Shopping Submissions Newsletters Magazine Subscription Shop DIY Books Buy Project Plans DIY University Follow UsMore Items Facebook Pinterest Instagram Twitter"
		}
	]
}
```
