## Radio Compatibility

Radios that have been specifically tested with KFD devices are listed below, along with any notes or firmware restrictions.

If you have used KFDtool with a radio that is not listed, please get in touch so we can update this list!

| Product line                 | Support status   | KFDtool software | KFD firmware | Radio firmware          | Notes |
|------------------------------|------------------|------------------|--------------|-------------------------|-------|
| Bendix King BK               | ❔ Untested      | —                | —            | —                       |
| Bendix King KNG              | ❔ Untested      | —                | —            | —                       |
| EF Johnson VP/VM 8000        | ✅ Tested        | ≥ 1.8.7          | ≥ 1.8.7      | Any                     |
| EF Johnson VP/VM x000        | ❔ Untested      | —                | —            | —                       |
| EF Johnson VP/VM x00         | ✅ Tested        | ≥ 1.8.7          | ≥ 1.8.7      | ≥ 8.28.5                |
| EF Johnson 5100/ES           | ✅ Tested        | ≥ 1.7.3          | ≥ 1.7.3      | ≥ 6.12.4                |
[^xtsmod]
| EF Johnson 5300/ES           | ❔ Untested      | —                | —            | —                       |
| Harris XL                    | ✅ Tested        | ≥ 1.8.7          | ≥ 1.8.7      | Any                     |
| Harris Unity (XG-100)        | ✅ Tested        | ≥ 1.8.7          | ≥ 1.8.7      | Any                     | [^ch100]
| Harris XG                    | ❔ Untested      | —                | —            | —                       | [^harrisxg]
| Kenwood NX                   | ✅ Tested        | ≥ 1.8.7          | ≥ 1.8.7      | Any                     | [^kenwood]
| Kenwood TK                   | ❔ Untested      | —                | —            | —                       | [^kenwood]
| Motorola APX (TWI)           | ✅ Tested        | ≥ 1.8.7          | ≥ 1.8.7      | Any                     |
| Motorola APX (DLI IP)        | ✅ Tested        | ≥ 1.8.7          | ≥ 1.8.7      | ≥ R27.03                | [^freon]
| Motorola ASTRO 25 (MACE)     | ✅ Tested        | ≥ 1.8.7          | ≥ 1.8.7      | Any                     |
| Motorola ASTRO 25 (UCM)      | ✅ Tested        | ≥ 1.8.7          | ≥ 1.8.7      | Any                     |
| Motorola ASTRO               | ✅ Tested        | ≥ 1.8.7          | ≥ 1.8.7      | ≥ R07.71.06, EMC R03.56 |
| Thales Liberty               | ✅ Tested        | ≥ 1.8.7          | ≥ 1.8.7      | Any                     |
| Tait TP/TM 9x00 series       | ❌ Not supported | —                | —            | —                       |

[^ch100]: XG-100M supports native TWI keyloading [^ch721] only via CH100
[^ch721]: XG-100M with CH721 supports TWI keyloading via Harris adapter cable 14002-0143-10
[^freon]: "Freon" (OMAP L-138) architecture only (APX 900, 6000 BN, 8000, 8500, NEXT, N-series, and BN mobiles)
[^harrisxg]: Harris XG radios require Harris adapter cable (portable: unknown part number; mobile: 14002-0143-10)
[^kenwood]: Requires SCM hardware module
[^xtsmod]: Can use a modified Motorola XTS Hirose adapter (part number NTN8613C). See the [Modifying an XTS Adapter](XTS Adapter Mod.md) page for more info