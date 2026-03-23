_The information in this guide applies to board version(s) v2 only_

# Ordering Boards From JLCPCB

 The production info for these boards has only been generated for JLCPCB. Using another manufacturer will require you to generate their required production information.

## Option 1: Ordering Assembled Boards from JLCPCB

1. Create an account on <https://jlcpcb.com> if you do not have one already
1. Go to <https://jlcpcb.com/parts> and upload the bom file found in `v2/src/production/OpenAquatix_v2_bom.csv` to the Bom tool. 
2. Select the quantity required and click "Process BOM"
3. Verify that the matched part count aligns with the expected value (129 for v2 TODO CHANGE ME) for the board. In case of discrepancies, please open an issue
4. Click on "Add All to My parts lib"
5. Go to <https://jlcpcb.com/user-center/smtPrivateLibrary/partsCart> and verify that the number of parts in the cart aligns with the number ordered in previous steps. In case of any discrepancies, first try to scroll down in the cart, but if only 100 parts get loaded, try switching browsers. Edge and Chrome have been observed to only load 100 parts in the cart while there have been no issues with Firefox. Once confirmed, checkout.
6. Some of the parts ordered in the previous step are "pre-ordered" meaning that they are not currently in-stock, but JLCPCB will attempt to source them from their suppliers. Typical lead times for these components are ~5-15 business days. If they cannot source a component, then they will notify you and you can either source the component from another supplier (Digikey, Mouser, etc.) and solder it yourself or send them the component (consign it). The latter option is not recommended as there are egregious shipping fees and delays. You can also try to substitute the component. JLCPCB will give you a quote ~2 days after the order is placed where you can either decide that the quoted price/shipping time is adequate or that it is too long and cancel the item.
7. Once all of the items have arrived in the JLCPCB parts library, you can begin the actual order for the assembled boards by uploading`v2/src/production/OpenAquatix_v2.zip` to <https://cart.jlcpcb.com/quote>.
8. Update the PCB order specifications as follows:
    1. `PCB Qty` -> The minimum multiple of 5 greater than the number of boards you need. E.g. 6 boards -> qty: 10.
    1. `Material Type` -> `FR4 TG155`
    2. `Specify Stackup` -> `Yes` and change `No Requirement` to `JLC06161H-3313`
9. Select `PCB Assembly` at the bottom of the page and change the following options:
    1. `PCBA Type` -> `Standard`
    2. `PCBA Qty` -> The number of boards you want to order
    3. (Optional) `Confirm Parts Placement` -> `Yes`. For advanced users only who could reasonably be able to detect any flaws with production files (unlikely but recommended for larger orders)
    4. `Bake Components` -> `Yes` and request that C2843785 is baked. This is the WS2812B LED
    5. (Optional, adds 1 day, but is cheap) `Depanel boards & edge rail before delivery` -> `Yes`
10. Click on `Next` on the right side column to get to the assembly details
11. Upload the BOM and positions files on the next screen
12. Place the board order

## Option 2: Assembling Boards Yourself
