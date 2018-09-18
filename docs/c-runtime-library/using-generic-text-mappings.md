---
title: Genel metin eşlemelerini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _UNICODE
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9435076bdc02f9f0b8a909ffdbc60dd06e1a388
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097529"
---
# <a name="using-generic-text-mappings"></a>Genel Metin Eşlemelerini Kullanma

**Microsoft'a özgü**

Çeşitli uluslararası pazarlar için kod geliştirmeyi basitleştirmek için çok sayıda veri türleri, yordamlar ve diğer nesneler için Microsoft çalışma zamanı kitaplığı Microsoft'a özgü "genel metin" eşlemeleri sağlar. Bu eşlemeler TCHAR içinde tanımlanır. H Herhangi bir karakter kümesi üç tür için derlenebilir genel kod yazmak için bu adı eşlemeleri kullanabilirsiniz: ASCII (SBCS), MBCS ve Unicode olarak kullanarak tanımladığınız bir bildirim sabiti bağlı olarak bir `#define` deyimi. Genel metin eşlemeleri ANSI uyumlu olmayan Microsoft uzantılarıdır.

### <a name="preprocessor-directives-for-generic-text-mappings"></a>Genel metin eşlemeleri için ön işlemci yönergeleri

|#define|Derlenmiş sürüm|Örnek|
|--------------|----------------------|-------------|
|`_UNICODE`|Unicode (geniş karakter)|`_tcsrev` Eşleyen `_wcsrev`|
|`_MBCS`|Çok baytlı karakter|`_tcsrev` Eşleyen `_mbsrev`|
|Hiçbiri (varsayılan: ne `_UNICODE` ya da `_MBCS` tanımlanan)|SBCS (ASCII)|`_tcsrev` Eşleyen `strrev`|

Örneğin, genel metin işlevi `_tcsrev`TCHAR içinde tanımlanmış. H, eşlenen `mbsrev` varsa `MBCS` programınızdaki veya için tanımlanan `_wcsrev` varsa `_UNICODE` tanımlanmış. Aksi takdirde `_tcsrev` eşlendiği `strrev`.

Genel metin veri türü `_TCHAR`TCHAR ayrıca tanımlanan. H eşler türüne `char` varsa `_MBCS` türü için tanımlanan `wchar_t` varsa `_UNICODE` tanımlanır ve türüne `char` hiçbiri sabiti tanımlanmışsa. Diğer veri türü eşlemeleri TCHAR sağlanır. Programlama kolaylık sağlamak için H ancak `_TCHAR` kullanışlıdır türü.

### <a name="generic-text-data-type-mappings"></a>Genel metin veri türü eşlemeleri

|Genel metin veri türü adı|SBCS (_UNICODE, _MBCS tanımlanmamış)|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|----------------------------------|--------------------------------------------|--------------------|-----------------------|
|`_TCHAR`|`char`|`char`|`wchar_t`|
|`_TINT`|`int`|`int`|`wint_t`|
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|
|`_T` veya `_TEXT`|Herhangi bir etkisi (önişlemci tarafından kaldırıldı)|Herhangi bir etkisi (önişlemci tarafından kaldırıldı)|`L` (aşağıdaki karakter veya Unicode çözümlemesiyle dizeye dönüştürür)|

Genel metin eşlemeleri yordamları, değişkenler ve diğer nesneler, tam bir listesi için bkz. [genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md).

Aşağıdaki kod parçalarını kullanımını gösteren `_TCHAR` ve `_tcsrev` eşleme MBCS, Unicode ve SBCS modelleri için.

```
_TCHAR *RetVal, *szString;
RetVal = _tcsrev(szString);
```

Varsa `MBCS` olmuştur tanımlanan, önişlemci önceki parça aşağıdaki kodu eşler:

```
char *RetVal, *szString;
RetVal = _mbsrev(szString);
```

Varsa `_UNICODE` olmuştur tanımlanan, önişlemci aynı parçaya aşağıdaki kodu eşler:

```
wchar_t *RetVal, *szString;
RetVal = _wcsrev(szString);
```

Kullanılmazsa `_MBCS` ya da `_UNICODE` olmuştur tanımlanan, önişlemci parça tek baytlık ASCII koduna şu şekilde eşlenir:

```
char *RetVal, *szString;
RetVal = strrev(szString);
```

Bu nedenle yazma, korumak ve herhangi bir karakter kümesi üç tür için özel yordamlar çalıştırmak için tek kaynak kod dosyasını derleyin.

 **END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Genel Metin Eşlemeleri](../c-runtime-library/generic-text-mappings.md)<br/>
[Veri Türü Eşlemeleri](../c-runtime-library/data-type-mappings.md)<br/>
[Sabit ve Global Değişken Eşlemeleri](../c-runtime-library/constant-and-global-variable-mappings.md)<br/>
[Rutin Eşlemeler](../c-runtime-library/routine-mappings.md)<br/>
[Örnek Genel Metin Programı](../c-runtime-library/a-sample-generic-text-program.md)