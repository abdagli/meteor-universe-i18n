<img src="http://uniproject.vazco.eu/black_logo.png" />
# Universe i18n

## Instalation
```sh
$ meteor add universe:i18n
```

## Usage

### Setting/Getting locale
```js
i18n.setLocale('en_us')
i18n.getLocale() //en_us
```

### Adding Translations
```js
import i18n from '{universe:i18n}';

i18n.addTranslation('en_us', 'common', 'no', 'No');
i18n.addTranslation('en_us.common', 'ok', 'Ok');
i18n.addTranslation('en_us.common.ok', 'Ok');

i18n.addTranslations('en_us', {
    common: {
        hello: 'Hello {$name} {$0}!'
    }
});

i18n.addTranslations('en_us', 'common', {
    hello: 'Hello {$name} {$0}!'
});
```

### Creating React component

```js

const T = i18n.createComponent();

// Later...
<T>common.no</T>
<T>common.ok</T>
<T name="World" {...[1]}>common.hello</T>
```

```js
const T = i18n.createComponent(i18n.createTranslator('common'));

// Later...
<T>no</T>
<T>ok</T>
<T name="World" {...[1]}>.hello</T>
```

### Formatting numbers

```js
i18n.parseNumber('7013217.715'); // 7,013,217.715
i18n.parseNumber('16217 and 17217,715'); // 16,217 and 17,217.715
i18n.parseNumber('7013217.715', 'ru_ru'); // 7 013 217,715
```

## API
```js
// create React component
i18n.createComponent(translator);

// create prefixed translator
i18n.createTranslator(prefix);

// add translation
i18n.addTranslation(prefix, key, translation);

// add translations
i18n.addTranslations(prefix, translationsMap);

// get translation
i18n.getTranslation(prefix, key, ..., params);
i18n.__(prefix, key,..., params);

// get translations
i18n.getTranslations(prefix, locale);

// options
i18n.options = {
    // opening string
    open: '{$',

    // closing string
    close: '}'
};

// formatting numbers for locale
i18n.parseNumber(number, locale);

// Setting locale
i18n.setLocale(locale)
// Getting locale
i18n.getLocale()

```

## Locales list
```
Locale   Language             Country  
    aa_DJ    Afar                 Djibouti                                   aa   DJ  
    aa_ER    Afar                 Eritrea                                    aa   ER  
    aa_ET    Afar                 Ethiopia                                   aa   ET  
    af_ZA    Afrikaans            South Africa                               af   ZA  
    am_ET    Amharic              Ethiopia                                   am   ET  
    an_ES    Aragonese            Spain                                      an   ES  
    ar_AE    Arabic               United Arab Emirates                       ar   AE  
    ar_BH    Arabic               Bahrain                                    ar   BH  
    ar_DZ    Arabic               Algeria                                    ar   DZ  
    ar_EG    Arabic               Egypt                                      ar   EG  
    ar_IN    Arabic               India                                      ar   IN  
    ar_IQ    Arabic               Iraq                                       ar   IQ  
    ar_JO    Arabic               Jordan                                     ar   JO  
    ar_KW    Arabic               Kuwait                                     ar   KW  
    ar_LB    Arabic               Lebanon                                    ar   LB  
    ar_LY    Arabic               Libyan Arab Jamahiriya                     ar   LY  
    ar_MA    Arabic               Morocco                                    ar   MA  
    ar_OM    Arabic               Oman                                       ar   OM  
    ar_QA    Arabic               Qatar                                      ar   QA  
    ar_SA    Arabic               Saudi Arabia                               ar   SA  
    ar_SD    Arabic               Sudan                                      ar   SD  
    ar_SY    Arabic               Syrian Arab Republic                       ar   SY  
    ar_TN    Arabic               Tunisia                                    ar   TN  
    ar_YE    Arabic               Yemen                                      ar   YE  
    as_IN    Assamese             India                                      as   IN  
    ast_ES   Asturian             Spain                                      ast  ES  
    az_AZ    Azerbaijani          Azerbaijan                                 az   AZ  
    be_BY    Byelorussian         Belarus                                    be   BY  
    ber_DZ   Berber               Algeria                                    ber  DZ  
    ber_MA   Berber               Morocco                                    ber  MA  
    bg_BG    Bulgarian            Bulgaria                                   bg   BG  
    bn_BD    Bengali/Bangla       Bangladesh                                 bn   BD  
    bn_IN    Bengali/Bangla       India                                      bn   IN  
    bo_CN    Tibetan              China                                      bo   CN  
    bo_IN    Tibetan              India                                      bo   IN  
    br_FR    Breton               France                                     br   FR  
    bs_BA    Bosnian              Bosnia And Herzegovina                     bs   BA  
    byn_ER   Bilin                Eritrea                                    byn  ER  
    ca_AD    Catalan              Andorra                                    ca   AD  
    ca_ES    Catalan              Spain                                      ca   ES  
    ca_FR    Catalan              France                                     ca   FR  
    ca_IT    Catalan              Italy                                      ca   IT  
    crh_UA   Crimean Tatar        Ukraine                                    crh  UA  
    cs_CZ    Czech                Czech Republic                             cs   CZ  
    csb_PL   Kashubian            Poland                                     csb  PL  
    cy_GB    Welsh                United Kingdom                             cy   GB  
    da_DK    Danish               Denmark                                    da   DK  
    de_AT    German               Austria                                    de   AT  
    de_BE    German               Belgium                                    de   BE  
    de_CH    German               Switzerland                                de   CH  
    de_DE    German               Germany                                    de   DE  
    de_LI    German               Liechtenstein                              de   LI  
    de_LU    German               Luxembourg                                 de   LU  
    dv_MV    Dhivehi              Maldives                                   dv   MV  
    dz_BT    Bhutani              Bhutan                                     dz   BT  
    el_CY    Greek                Cyprus                                     el   CY  
    el_GR    Greek                Greece                                     el   GR  
    en_AG    English              Antigua And Barbuda                        en   AG  
    en_AU    English              Australia                                  en   AU  
    en_BW    English              Botswana                                   en   BW  
    en_CA    English              Canada                                     en   CA  
    en_DK    English              Denmark                                    en   DK  
    en_GB    English              United Kingdom                             en   GB  
    en_HK    English              Hong Kong                                  en   HK  
    en_IE    English              Ireland                                    en   IE  
    en_IN    English              India                                      en   IN  
    en_NG    English              Nigeria                                    en   NG  
    en_NZ    English              New Zealand                                en   NZ  
    en_PH    English              Philippines                                en   PH  
    en_SG    English              Singapore                                  en   SG  
    en_US    English              United States                              en   US  
    en_ZA    English              South Africa                               en   ZA  
    en_ZW    English              Zimbabwe                                   en   ZW  
    eo       Esperanto                                                       eo       
    es_AR    Spanish              Argentina                                  es   AR  
    es_BO    Spanish              Bolivia                                    es   BO  
    es_CL    Spanish              Chile                                      es   CL  
    es_CO    Spanish              Colombia                                   es   CO  
    es_CR    Spanish              Costa Rica                                 es   CR  
    es_DO    Spanish              Dominican Republic                         es   DO  
    es_EC    Spanish              Ecuador                                    es   EC  
    es_ES    Spanish              Spain                                      es   ES  
    es_GT    Spanish              Guatemala                                  es   GT  
    es_HN    Spanish              Honduras                                   es   HN  
    es_MX    Spanish              Mexico                                     es   MX  
    es_NI    Spanish              Nicaragua                                  es   NI  
    es_PA    Spanish              Panama                                     es   PA  
    es_PE    Spanish              Peru                                       es   PE  
    es_PR    Spanish              Puerto Rico                                es   PR  
    es_PY    Spanish              Paraguay                                   es   PY  
    es_SV    Spanish              El Salvador                                es   SV  
    es_US    Spanish              United States                              es   US  
    es_UY    Spanish              Uruguay                                    es   UY  
    es_VE    Spanish              Venezuela                                  es   VE  
    et_EE    Estonian             Estonia                                    et   EE  
    eu_ES    Basque               Spain                                      eu   ES  
    eu_FR    Basque               France                                     eu   FR  
    fa_IR    Persian              Iran, Islamic Republic Of                  fa   IR  
    fi_FI    Finnish              Finland                                    fi   FI  
    fil_PH   Filipino             Philippines                                fil  PH  
    fo_FO    Faeroese             Faroe Islands                              fo   FO  
    fr_BE    French               Belgium                                    fr   BE  
    fr_CA    French               Canada                                     fr   CA  
    fr_CH    French               Switzerland                                fr   CH  
    fr_FR    French               France                                     fr   FR  
    fr_LU    French               Luxembourg                                 fr   LU  
    fur_IT   Friulian             Italy                                      fur  IT  
    fy_DE    Frisian              Germany                                    fy   DE  
    fy_NL    Frisian              Netherlands                                fy   NL  
    ga_IE    Irish                Ireland                                    ga   IE  
    gd_GB    Scots/Gaelic         United Kingdom                             gd   GB  
    gez_ER   Geez                 Eritrea                                    gez  ER  
    gez_ET   Geez                 Ethiopia                                   gez  ET  
    gl_ES    Galician             Spain                                      gl   ES  
    gu_IN    Gujarati             India                                      gu   IN  
    gv_GB    Manx                 United Kingdom                             gv   GB  
    ha_NG    Hausa                Nigeria                                    ha   NG  
    he_IL    Hebrew               Israel                                     he   IL  
    hi_IN    Hindi                India                                      hi   IN  
    hne_IN   Chhattisgarhi        India                                      hne  IN  
    hr_HR    Croatian             Croatia                                    hr   HR  
    hsb_DE   Upper Sorbian        Germany                                    hsb  DE  
    ht_HT    Haitian              Haiti                                      ht   HT  
    hu_HU    Hungarian            Hungary                                    hu   HU  
    hy_AM    Armenian             Armenia                                    hy   AM  
    ia       Interlingua                                                     ia       
    id_ID    Indonesian           Indonesia                                  id   ID  
    ig_NG    Igbo                 Nigeria                                    ig   NG  
    ik_CA    Inupiak              Canada                                     ik   CA  
    is_IS    Icelandic            Iceland                                    is   IS  
    it_CH    Italian              Switzerland                                it   CH  
    it_IT    Italian              Italy                                      it   IT  
    iu_CA    Inuktitut            Canada                                     iu   CA  
    iw_IL    Hebrew               Israel                                     iw   IL  
    ja_JP    Japanese             Japan                                      ja   JP  
    ka_GE    Georgian             Georgia                                    ka   GE  
    kk_KZ    Kazakh               Kazakhstan                                 kk   KZ  
    kl_GL    Greenlandic          Greenland                                  kl   GL  
    km_KH    Cambodian            Cambodia                                   km   KH  
    kn_IN    Kannada              India                                      kn   IN  
    ko_KR    Korean               Korea, Republic Of                         ko   KR  
    ks_IN    Kashmiri             India                                      ks   IN  
    ku_TR    Kurdish              Turkey                                     ku   TR  
    kw_GB    Cornish              United Kingdom                             kw   GB  
    ky_KG    Kirghiz              Kyrgyzstan                                 ky   KG  
    lg_UG    Ganda                Uganda                                     lg   UG  
    li_BE    Limburgan            Belgium                                    li   BE  
    li_NL    Limburgan            Netherlands                                li   NL  
    lo_LA    Laothian             Lao People's Democratic Republic           lo   LA  
    lt_LT    Lithuanian           Lithuania                                  lt   LT  
    lv_LV    Latvian/Lettish      Latvia                                     lv   LV  
    mai_IN   Maithili             India                                      mai  IN  
    mg_MG    Malagasy             Madagascar                                 mg   MG  
    mi_NZ    Maori                New Zealand                                mi   NZ  
    mk_MK    Macedonian           Macedonia, The Former Yugoslav Republic Of mk   MK  
    ml_IN    Malayalam            India                                      ml   IN  
    mn_MN    Mongolian            Mongolia                                   mn   MN  
    mr_IN    Marathi              India                                      mr   IN  
    ms_MY    Malay                Malaysia                                   ms   MY  
    mt_MT    Maltese              Malta                                      mt   MT  
    my_MM    Burmese              Myanmar                                    my   MM  
    nb_NO    Norwegian Bokmål     Norway                                     nb   NO  
    nds_DE   Low German           Germany                                    nds  DE  
    nds_NL   Low German           Netherlands                                nds  NL  
    ne_NP    Nepali               Nepal                                      ne   NP  
    nl_AW    Dutch                Aruba                                      nl   AW  
    nl_BE    Dutch                Belgium                                    nl   BE  
    nl_NL    Dutch                Netherlands                                nl   NL  
    nn_NO    Norwegian Nynorsk    Norway                                     nn   NO  
    no_NO    Norwegian            Norway                                     no   NO  
    nr_ZA    South Ndebele        South Africa                               nr   ZA  
    nso_ZA   Pedi                 South Africa                               nso  ZA  
    oc_FR    Occitan              France                                     oc   FR  
    om_ET    (Afan)/Oromoor/Oriya Ethiopia                                   om   ET  
    om_KE    (Afan)/Oromoor/Oriya Kenya                                      om   KE  
    or_IN    Oriya                India                                      or   IN  
    pa_IN    Punjabi              India                                      pa   IN  
    pa_PK    Punjabi              Pakistan                                   pa   PK  
    pap_AN   Papiamento           Netherlands Antilles                       pap  AN  
    pl_PL    Polish               Poland                                     pl   PL  
    ps_AF    Pashto/Pushto        Afghanistan                                ps   AF  
    pt_BR    Portuguese           Brazil                                     pt   BR  
    pt_PT    Portuguese           Portugal                                   pt   PT  
    ro_RO    Romanian             Romania                                    ro   RO  
    ru_RU    Russian              Russian Federation                         ru   RU  
    ru_UA    Russian              Ukraine                                    ru   UA  
    rw_RW    Kinyarwanda          Rwanda                                     rw   RW  
    sa_IN    Sanskrit             India                                      sa   IN  
    sc_IT    Sardinian            Italy                                      sc   IT  
    sd_IN    Sindhi               India                                      sd   IN  
    se_NO    Northern Sami        Norway                                     se   NO  
    shs_CA   Shuswap              Canada                                     shs  CA  
    si_LK    Singhalese           Sri Lanka                                  si   LK  
    sid_ET   Sidamo               Ethiopia                                   sid  ET  
    sk_SK    Slovak               Slovakia                                   sk   SK  
    sl_SI    Slovenian            Slovenia                                   sl   SI  
    so_DJ    Somali               Djibouti                                   so   DJ  
    so_ET    Somali               Ethiopia                                   so   ET  
    so_KE    Somali               Kenya                                      so   KE  
    so_SO    Somali               Somalia                                    so   SO  
    sq_AL    Albanian             Albania                                    sq   AL  
    sr_CS    Serbian              Serbia And Montenegro                      sr   CS  
    sr_ME    Serbian                                                         sr   ME  
    sr_RS    Serbian                                                         sr   RS  
    sr_YU    Serbian                                                         sr   YU  
    ss_ZA    Siswati              South Africa                               ss   ZA  
    st_ZA    Sesotho              South Africa                               st   ZA  
    sv_FI    Swedish              Finland                                    sv   FI  
    sv_SE    Swedish              Sweden                                     sv   SE  
    ta_IN    Tamil                India                                      ta   IN  
    te_IN    Tegulu               India                                      te   IN  
    tg_TJ    Tajik                Tajikistan                                 tg   TJ  
    th_TH    Thai                 Thailand                                   th   TH  
    ti_ER    Tigrinya             Eritrea                                    ti   ER  
    ti_ET    Tigrinya             Ethiopia                                   ti   ET  
    tig_ER   Tigre                Eritrea                                    tig  ER  
    tk_TM    Turkmen              Turkmenistan                               tk   TM  
    tl_PH    Tagalog              Philippines                                tl   PH  
    tn_ZA    Setswana             South Africa                               tn   ZA  
    tr_CY    Turkish              Cyprus                                     tr   CY  
    tr_TR    Turkish              Turkey                                     tr   TR  
    ts_ZA    Tsonga               South Africa                               ts   ZA  
    tt_RU    Tatar                Russian Federation                         tt   RU  
    ug_CN    Uighur               China                                      ug   CN  
    uk_UA    Ukrainian            Ukraine                                    uk   UA  
    ur_PK    Urdu                 Pakistan                                   ur   PK  
    uz_UZ    Uzbek                Uzbekistan                                 uz   UZ  
    ve_ZA    Venda                South Africa                               ve   ZA  
    vi_VN    Vietnamese           Viet Nam                                   vi   VN  
    wa_BE    Walloon              Belgium                                    wa   BE  
    wo_SN    Wolof                Senegal                                    wo   SN  
    xh_ZA    Xhosa                South Africa                               xh   ZA  
    yi_US    Yiddish              United States                              yi   US  
    yo_NG    Yoruba               Nigeria                                    yo   NG  
    zh_CN    Chinese              China                                      zh   CN  
    zh_HK    Chinese              Hong Kong                                  zh   HK  
    zh_SG    Chinese              Singapore                                  zh   SG  
    zh_TW    Chinese              Taiwan, Province Of China                  zh   TW  
    zu_ZA    Zulu                 South Africa                               zu   ZA  
```
