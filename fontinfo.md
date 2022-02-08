# Family-level info

* copyright
* familyName
* note
* openTypeGaspRangeRecords # list of dict
* openTypeHeadCreated
* openTypeHeadFlags
* openTypeHeadLowestRecPPEM
* openTypeNameCompatibleFullName
* openTypeNameDescription
* openTypeNameDesigner
* openTypeNameDesignerURL
* openTypeNameLicense
* openTypeNameLicenseURL
* openTypeNameManufacturer
* openTypeNameManufacturerURL
* openTypeNamePreferredFamilyName
* openTypeNameRecords # list of dict
* openTypeNameSampleText
* openTypeNameUniqueID
* openTypeNameVersion
* openTypeNameWWSFamilyName
* openTypeOS2CodePageRanges (Or source-level?)
* openTypeOS2FamilyClass
* openTypeOS2Type
* openTypeOS2UnicodeRanges (Or source-level?)
* openTypeOS2VendorID
* postscriptBlueFuzz
* postscriptBlueScale
* postscriptBlueShift
* postscriptDefaultCharacter
* postscriptDefaultWidthX
* postscriptFamilyBlues
* postscriptFamilyOtherBlues
* postscriptIsFixedPitch
* postscriptNominalWidthX
* postscriptWindowsCharacterSet
* trademark
* unitsPerEm
* versionMajor
* versionMinor

# Source/master-level info

* ascender
* capHeight
* descender
* guidelines # list of dict
* italicAngle
* openTypeHheaAscender
* openTypeHheaCaretOffset
* openTypeHheaCaretSlopeRise
* openTypeHheaCaretSlopeRun
* openTypeHheaDescender
* openTypeHheaLineGap
* openTypeNamePreferredSubfamilyName
* openTypeNameWWSSubfamilyName
* openTypeOS2Panose
* openTypeOS2Selection
* openTypeOS2StrikeoutPosition
* openTypeOS2StrikeoutSize
* openTypeOS2SubscriptXOffset
* openTypeOS2SubscriptXSize
* openTypeOS2SubscriptYOffset
* openTypeOS2SubscriptYSize
* openTypeOS2SuperscriptXOffset
* openTypeOS2SuperscriptXSize
* openTypeOS2SuperscriptYOffset
* openTypeOS2SuperscriptYSize
* openTypeOS2TypoAscender
* openTypeOS2TypoDescender
* openTypeOS2TypoLineGap
* openTypeOS2WeightClass
* openTypeOS2WidthClass
* openTypeOS2WinAscent
* openTypeOS2WinDescent
* openTypeVheaCaretOffset
* openTypeVheaCaretSlopeRise
* openTypeVheaCaretSlopeRun
* openTypeVheaVertTypoAscender
* openTypeVheaVertTypoDescender
* openTypeVheaVertTypoLineGap
* postscriptBlueValues
* postscriptFontName
* postscriptForceBold
* postscriptFullName
* postscriptOtherBlues
* postscriptSlantAngle
* postscriptStemSnapH
* postscriptStemSnapV
* postscriptUnderlinePosition
* postscriptUnderlineThickness
* postscriptUniqueID
* postscriptWeightName
* styleMapFamilyName
* styleMapStyleName
* styleName
* xHeight

# Ignored info

* macintoshFONDFamilyID
* macintoshFONDName
* woffMajorVersion
* woffMetadataCopyright
* woffMetadataCredits
* woffMetadataDescription
* woffMetadataExtensions
* woffMetadataLicense
* woffMetadataLicensee
* woffMetadataTrademark
* woffMetadataUniqueID
* woffMetadataVendor
* woffMinorVersion
* year


# Multi-file approach

fontinfo.csv
fontinfo.gasp.csv
fontinfo.license.txt  # free-form text files
fontinfo.name_records.csv
fontinfo.note.txt  # free-form text files
fontinfo.sample_text.txt  # free-form text files
sourceinfo.csv
sourceinfo.guidelines.csv
layerinfo.color_marks.csv
layerinfo.json
sourcelib.json # per source, in set.default

## fontinfo.gasp.csv

```csv
rangeMaxPPEM,rangeGaspBehavior
7,1 3
65535,0 1 2 3
```

## fontinfo.name_records.csv

```csv
encodingID,languageID,nameID,platformID,string
0,0,3,1,Unique Font Identifier
1,1033,8,3,Some Foundry (Manufacturer Name)
```
## sourceinfo.guidelines.csv

```csv
x,y,angle,name,color,identifier
,300,,hello,,
100,,,bla,,
1,2,3,xyz,,
```

## layerinfo.color_marks.csv

```csv
name,color
a,"1,1,1,1"
```

# Example file trees

* ExampleMetadata.fontgarden/
    * fontinfo.csv
    * fontinfo.gasp.csv
    * fontinfo.license.txt
    * fontinfo.name_records.csv
    * fontinfo.note.txt
    * fontinfo.sample_text.txt
    * sourceinfo.csv
    * set.default
        * source.Regular
            * glyphs
                * a.glif
                * layerinfo.color_marks.csv
                * layerinfo.plist
            * sourceinfo.guidelines.csv
            * sourcelib.plist

---

* NotoSans.fontgarden/
    * fontinfo.csv
    * sourceinfo.csv
    * set.default
        * source.Light
            * sourcelib.plist
        * source.Bold
            * sourcelib.plist
        * source.CondensedLight
            * sourcelib.plist
        * source.CondensedBold
            * sourcelib.plist
    * set.Latin
        * glyph_data.csv
        * source.Light
            * glyphs
                * A_.glif
                * B_.glif
            * kerning.csv
            * layerinfo.plist
            * layerinfo.color_marks.plist
        * source.Bold
            * glyphs
                * A_.glif
                * B_.glif
            * kerning.csv
        * source.CondensedLight
            * glyphs
                * A_.glif
                * B_.glif
            * kerning.csv
        * source.CondensedBold
            * glyphs
                * A_.glif
                * B_.glif
            * kerning.csv

---

* NotoSans.fontgarden/
    * fontinfo.csv
    * sourceinfo.csv
    * set.default
        * source.Light
            * sourcelib.plist
        * source.Bold
            * sourcelib.plist
        * source.CondensedLight
            * sourcelib.plist
        * source.CondensedBold
            * sourcelib.plist
    * set.Latin
        * glyph_data.csv
        * source.Light
            * glyphs
                * A_.glif
                * B_.glif
            * kerning.csv
            * layerinfo.plist
            * layerinfo.color_marks.plist
        * source.Bold
            * glyphs
                * A_.glif
                * B_.glif
            * kerning.csv
        * source.CondensedLight
            * glyphs
                * A_.glif
                * B_.glif
            * kerning.csv
        * source.CondensedBold
            * glyphs
                * A_.glif
                * B_.glif
            * kerning.csv
    * set.Cyrillic
        * glyph_data.csv
        * source.Light
            * glyphs
                * A_-cy.glif
                * Be_-cy.glif
            * kerning.csv
        * source.Bold
            * glyphs
                * A_-cy.glif
                * Be_-cy.glif
            * kerning.csv
        * source.CondensedLight
            * glyphs
                * A_-cy.glif
                * Be_-cy.glif
            * kerning.csv
        * source.CondensedBold
            * glyphs
                * A_-cy.glif
                * Be_-cy.glif
            * kerning.csv

---

* NotoSans.fontgarden/
    * …
    * set.default
        * …
    * set.Cyrillic
        * …
    * set.Latin
        * …
    * set.Modi
        * glyph_data.csv
        * source.Regular
            * glyphs
                * A_A__dv.alt.glif

---

* NotoSans.fontgarden/
    * …
    * set.default
        * …
    * set.Cyrillic
        * …
    * set.Latin
        * glyph_data.csv
        * source.Light
            * glyphs
                * A_.glif
            * kerning.csv
            * layerinfo.plist
            * layerinfo.color_marks.plist
        * source.Bold
            * glyphs
                * A_.glif
            * kerning.csv
        * source.CondensedLight
            * glyphs
                * A_.glif
            * kerning.csv
        * source.CondensedBold
            * glyphs
                * A_.glif
            * kerning.csv
    * set.LatinOther
        * glyph_data.csv
        * source.Light
            * glyphs
                * B_.glif
            * kerning.csv
        * source.Bold
            * glyphs
                * B_.glif
            * kerning.csv
        * source.CondensedLight
            * glyphs
                * B_.glif
            * kerning.csv
        * source.CondensedBold
            * glyphs
                * B_.glif
            * kerning.csv
    * set.Modi
        * ...
