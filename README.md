# mfc_keys_FR

An exhaustive search over a dictionary is one of the simplest technics that you can conduct on Mifare Classic chips, and sometimes, the only viable one on embedded readers/tools such as the proxmark3. Various dictionaries exist online but are generally huge, without the ability to easily filter it, leading to a long exhaustive search runtime.

**The repository focuses on compiling keys that are commonly used by Mifare Classic devices in France and neighboring countries**

All of these keys are well known and come from various publicly available sources (see references in the dictionary file).

## Contribution

New keys obtained by research on tags or by online findings are welcome. Send your pull request.

## Methodology

1. Find various key sources
2. Parse each key subcategory of each source (brand/company subcategories)
3. Identify subcategories of brand known to sell device in the country
4. Append identified subcategories to dict and try to define priorities
5. Find conflicting keys in the file (same key belonging to two different brand/device subcategories)
6.  Add the whole conflicting subcategory and keep only one occurrence of the conflicting key (comment the other). Adjust priorities if needed.
7. Loop to step 5 depending on the level of accuracy that you want

## Usage

Most common Mifare Classic tools with dictionary search features use the same file format (one key per line). So `mfc_keys_fr.dic` just needs to be renamed according to the tool.

### Flipper Zero

Install path : `external_storage/nfc/assets/mf_classic_dict_user.nfc`

`mf_classic_dict_user.nfc` will get parsed prior to the official flipper dictionary `mf_classic_dict.nfc`. If the user dictionary was useless, the flipper will fall back to the normal dictionary.

### Proxmark3

**Client**
Dictionaries are located at `client\dictionaries`

**Standalone mode**
*todo*

