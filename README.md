# eth-prague-2023
<h2>Warehouse Shipment and Item Generator</h2>

<h3>Context:</h3>
A case can be made for creating a digital twin for physical consumer goods.  In this instance, the digital twin functions like a paper receipt.  It can store information about the purchase transaction but go a step further and provide detailed provenance information, warranty information, LCA / carbon impact information and more.  This digital twin can fulfill the role of a 'Digital Product Passport' which is a coming requirement in the EU for disclosing more product information.

This project will create a system which generates ERC721 tokens and connects these tokens to the physical item.  The issuer of these tokens will be the warehouse where the items are received and then shipped, in this example to final consumers.  The 'warehouse' is assumed to be controlled by the business entity responsible for the production and/or retailer of the items.

<h3>Components of the Project:</h3>

<h4>Shipment Factory Contract:</h4>
Makes Shipment Contract (ERC 721) based on a request from the Warehouse Application

<h4>Consumer Item Factory Contract:</h4>
Makes Item Contract (ERC 721) based on request from the Warehouse Application

<h4>Warehouse Application:</h4>
The warehouse application in this project will be a django project that contains a list of the Shipments and Consumer Items which pass through it.  It will create pages for viewing information about the Shipments and Consumer items.   It will also store the private key of a EOA and use web3.py to communicate to the blockchain.

It will also use the Shipment Factory Contract and the Consumer Item Factory Contract to make a Shipment Contract and Consumer Item Contract for its own activities.  

There will be 8 pages in the Warehouse Application:

<h5>1. Create Shipment Contract</h5>
	- Enter information necessary to create the shipment contract and mint

<h5>2. Create Item Contract</h5>
	- Enter information necessary to create the item contract and mint

<h5>3. Create Shipment Token</h5>
	- Enter information necessary to create a shipment token on the aforementioned contract
	- Include the IDs of all items within that shipment
	- URL created to provide all this information, this URL is the barcode of the item

<h5>4. Create Item Token Information</h5>
	- Create a web page that will become the tokenuri of the token corresponding to the physical item.  Ideally, it will also contain the ID of the inbound shipment on which it was received
	- Note that:
Warehouses do not want to actually issue the NFT digital twin at the time of shipment.  This is because the further they can delay the minting of the digital twin the more information about the downstream journey can be included.  For instance, if the truck that delivers the item from the warehouse to the customer is an electric vehicle, this information can be incorporated into the environmental footprint of the item.  The best scenario would be that the final retailer or consumer can mint the token associated with the item.

<h5>5. Shipment Information Page</h5>
	- Can display information about the shipments

<h5>6. Item Information Page</h5>
	- Can display information about the shipments

<h5>7. List Shipments</h5>
	- Display a list of all shipments and their status

<h5>8. List Items</h5>
	- Display a list of all items and their status

<h3>General Notes:</h3>
For this project, user permissions will not be managed, we can assume that there is one warehouse user that has one EOA that can do everything.   
The identifier for all shipments and items will be a UUID.
The identifier for all tokens will be the integer version of this UUID.
The more detail that can be accomplished, the better.

