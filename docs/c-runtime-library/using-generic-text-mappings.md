---
title: Genel Metin Eşlemelerini Kullanma
ms.date: 11/04/2016
f1_keywords:
- _UNICODE
helpviewer_keywords:
- _TXCHAR type
- TINT type
- _TCHAR type
- TSCHAR type
- TEXT type
- TCHAR type
- TCHAR.H data types, mappings defined in
- generic-text data types
- _TINT type
- TUCHAR type
- _UNICODE constant
- TXCHAR type
- generic-text mappings
- _TSCHAR type
- T type
- mappings, generic-text
- _TUCHAR type
- MBCS data type
- _MBCS data type
- _TEXT type
- UNICODE constant
- _T type
ms.assetid: 2848121c-e51f-4b9b-a2e6-833ece4b0cb3
ms.openlocfilehash: f8616e0ff660b299544ed3c2f0a12feb4dbfe66b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221880"
---
# <a name="using-generic-text-mappings"></a>Genel Metin Eşlemelerini Kullanma

**Microsoft'a Özgü**

Çeşitli uluslararası pazarlar için kod geliştirmeyi basitleştirmek amacıyla, Microsoft çalışma zamanı kitaplığı birçok veri türü, yordamlar ve diğer nesneler için Microsoft 'a özgü "genel metin" eşlemeleri sağlar. Bu eşlemeler TCHAR içinde tanımlanmıştır. Olsun. Bu ad eşlemelerini, bir ifade kullanarak tanımladığınız bir bildirim sabitine bağlı olarak, üç tür karakter kümesi için derlenebilecek genel kod yazmak üzere kullanabilirsiniz: ASCII (SBCS), MBCS veya Unicode `#define` . Genel metin eşlemeleri, ANSI uyumlu olmayan Microsoft uzantılarıdır.

### <a name="preprocessor-directives-for-generic-text-mappings"></a>Genel metin eşlemeleri için Önişlemci yönergeleri

|#define|Derlenmiş sürüm|Örnek|
|--------------|----------------------|-------------|
|`_UNICODE`|Unicode (geniş karakter)|`_tcsrev`eşleme`_wcsrev`|
|`_MBCS`|Çok baytlı karakter|`_tcsrev`eşleme`_mbsrev`|
|Hiçbiri (varsayılan: ne `_UNICODE` de `_MBCS` tanımlanmamış)|SBCS (ASCıı)|`_tcsrev`eşleme`strrev`|

Örneğin, TCHAR içinde tanımlanan genel metin işlevi `_tcsrev` . H, `mbsrev` `MBCS` programınızda tanımlanmışsa veya tanımlanmışsa öğesine eşlenir `_wcsrev` `_UNICODE` . Aksi takdirde `_tcsrev` ile eşlenir `strrev` .

`_TCHAR`TCHAR içinde de tanımlanan genel metin veri türü. H, tanımlanmışsa tür ile eşlenir, **`char`** `_MBCS` **`wchar_t`** `_UNICODE` tanımlıysa yazın ve **`char`** her iki sabit tanımlı değilse yazın. Diğer veri türü eşlemeleri TCHAR içinde verilmiştir. Programlama kolaylığı için H, ancak `_TCHAR` en faydalı türdür.

### <a name="generic-text-data-type-mappings"></a>Genel metin veri türü eşlemeleri

|Genel metin veri türü adı|SBCS (_UNICODE, _MBCS tanımlanmadı)|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|----------------------------------|--------------------------------------------|--------------------|-----------------------|
|`_TCHAR`|**`char`**|**`char`**|**`wchar_t`**|
|`_TINT`|**`int`**|**`int`**|`wint_t`|
|`_TSCHAR`|**`signed char`**|**`signed char`**|**`wchar_t`**|
|`_TUCHAR`|**`unsigned char`**|**`unsigned char`**|**`wchar_t`**|
|`_TXCHAR`|**`char`**|**`unsigned char`**|**`wchar_t`**|
|`_T` veya `_TEXT`|Efekt yok (ön işlemci tarafından kaldırıldı)|Efekt yok (ön işlemci tarafından kaldırıldı)|`L`(aşağıdaki karakter veya dizeyi Unicode karşılığına dönüştürür)|

Yordamların, değişkenlerin ve diğer nesnelerin genel metin eşlemelerinin tam bir listesi için bkz. [Genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md).

Aşağıdaki kod parçaları `_TCHAR` `_tcsrev` MBCS, UNICODE ve SBCS modellerine eşleme için ve kullanımını gösterir.

```
_TCHAR *RetVal, *szString;
RetVal = _tcsrev(szString);
```

`MBCS`Tanımlanmışsa, ön işlemci önceki parçayı aşağıdaki kodla eşler:

```
char *RetVal, *szString;
RetVal = _mbsrev(szString);
```

`_UNICODE`Tanımlanmışsa, ön işlemci aynı parçayı aşağıdaki kodla eşler:

```
wchar_t *RetVal, *szString;
RetVal = _wcsrev(szString);
```

Ne `_MBCS` de `_UNICODE` tanımlı değilse, ön işlemci parçayı şu şekilde tek baytlı ASCII koduna eşler:

```
char *RetVal, *szString;
RetVal = strrev(szString);
```

Bu nedenle, üç tür karakter kümesinden birine özgü yordamlar ile çalışacak tek bir kaynak kod dosyası yazabilir, bakımını yapabilir ve derleyebilirsiniz.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md)<br/>
[Veri türü eşlemeleri](../c-runtime-library/data-type-mappings.md)<br/>
[Sabit ve global değişken eşlemeleri](../c-runtime-library/constant-and-global-variable-mappings.md)<br/>
[Rutin eşlemeler](../c-runtime-library/routine-mappings.md)<br/>
[Örnek bir genel metin programı](../c-runtime-library/a-sample-generic-text-program.md)
