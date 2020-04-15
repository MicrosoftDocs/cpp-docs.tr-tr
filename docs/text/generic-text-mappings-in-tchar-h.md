---
title: Tchar.h'deki Genel Metin Eşlemeleri
ms.date: 11/04/2016
helpviewer_keywords:
- mapping generic-text
- generic-text mappings [C++]
- character sets [C++], generic-text mappings
- Unicode [C++], generic-text mappings
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 01e1bb74-5a01-4093-8720-68b6c1fdda80
ms.openlocfilehash: bf872df2e6fb49e64a973e8799eef98dec1cb472
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361352"
---
# <a name="generic-text-mappings-in-tcharh"></a>Tchar.h'deki Genel Metin Eşlemeleri

Microsoft çalışma zamanı kitaplığı, uluslararası kullanım için kodun taşınmasını kolaylaştırmak için, birçok veri türü, yordam ve diğer nesneler için Microsoft'a özgü genel metin eşlemeleri sağlar. Tchar.h'de tanımlanan bu eşlemeleri, bir `#define` deyim kullanarak tanımladığınız bir bildirim sabitine bağlı olarak tek bayt, çok bayt veya Unicode karakter kümeleri için derlenebilecek genel kod yazmak için kullanabilirsiniz. Genel metin eşlemeleri, ANSI uyumlu olmayan Microsoft uzantılarıdır.

tchar.h'yi kullanarak, aynı kaynaklardan tek bayt, Multibayt Karakter Kümesi (MBCS) ve Unicode uygulamaları oluşturabilirsiniz. tchar.h, doğru önişlemci tanımlarıyla `_tcs`, `str`yani `_mbs` `wcs` işlevlerin eşlenediğini (öneki olan) makroları tanımlar. MBCS oluşturmak için sembolü `_MBCS`tanımlayın. Unicode oluşturmak için, `_UNICODE`sembolü tanımlayın. Tek bayt uygulaması oluşturmak için, ne (varsayılan) tanımlayın. Varsayılan olarak, `_UNICODE` MFC uygulamaları için tanımlanır.

Veri `_TCHAR` türü tchar.h'de koşullu olarak tanımlanır. Sembol yapınız için `_UNICODE` tanımlanmışsa, `_TCHAR` **wchar_t**olarak tanımlanır; aksi takdirde, tek bayt ve MBCS oluşturur için, **bu char**olarak tanımlanır. (**wchar_t**, temel Unicode geniş karakterli veri türü, 8-bit imzalı **char**16-bit muadilidir .) Uluslararası uygulamalar için, `_tcs` bayt lar yerine `_TCHAR` birimler halinde çalışan fonksiyonlar ailesini kullanın. Örneğin, `_tcsncpy` kopyalar, `n` `_TCHARs` `n` bayt değil.

Bazı Single Byte Karakter Kümesi (SBCS) dize `char*` işleme işlevleri parametreleri aldığından (imzalı) parametreleri, tanımlandığında `_MBCS` bir tür uyumsuzluğu derleyici uyarı sonuçları. Bu uyarıyı önlemenin üç yolu vardır:

1. Tchar.h'deki tip güvenli satır içi işlevini kullanın. Bu varsayılan davranıştır.

1. Komut satırında tanımlayarak `_MB_MAP_DIRECT` tchar.h'deki doğrudan makroları kullanın. Bunu yaparsanız, türleri el ile eşleştirmeniz gerekir. Bu en hızlı yöntemdir, ancak tür güvenli değildir.

1. Tchar.h'deki tür-güvenli statik bağlı kitaplık işlevini kullanın. Bunu yapmak için komut `_NO_INLINING` satırındaki sabiti tanımlayın. Bu en yavaş yöntemdir, ancak en çok tür güvenlidir.

### <a name="preprocessor-directives-for-generic-text-mappings"></a>Genel Metin Eşlemeleri için Önİşlemci Yönergeleri

|# tanımlamak|Derlenmiş sürüm|Örnek|
|---------------|----------------------|-------------|
|`_UNICODE`|Unicode (geniş karakterli)|`_tcsrev`için haritalar`_wcsrev`|
|`_MBCS`|Çok bayt karakter|`_tcsrev`için haritalar`_mbsrev`|
|Yok (varsayılan ne `_UNICODE` `_MBCS` de tanımlanmış)|SBCS (ASCII)|`_tcsrev`için haritalar`strrev`|

Örneğin, tchar.h'de tanımlanan genel metin `_tcsrev`işlevi, programınızda tanımlayıp tanımladığınızı `_wcsrev` veya `_UNICODE`tanımladığınız `_mbsrev` `_MBCS` için eşler. Aksi `_tcsrev` takdirde, `strrev`haritalar . Diğer veri türü eşlemeleri programlama kolaylığı için tchar.h'de sağlanır, ancak `_TCHAR` en kullanışlı olandır.

### <a name="generic-text-data-type-mappings"></a>Genel Metin Veri Türü Eşlemeleri

|Genel Metin<br /> Veri Türü Adı|_UNICODE &<br /> _MBCS Tanımlanmamış|_mbcs<br /> Tanımlanan|_unıcode<br /> Tanımlanan|
|--------------------------------------|----------------------------------------|------------------------|---------------------------|
|`_TCHAR`|**char**|**char**|**wchar_t**|
|`_TINT`|**int**|**unsigned int**|`wint_t`|
|`_TSCHAR`|**imzalı char**|**imzalı char**|**wchar_t**|
|`_TUCHAR`|**unsigned char**|**unsigned char**|**wchar_t**|
|`_TXCHAR`|**char**|**unsigned char**|**wchar_t**|
|`_T` veya `_TEXT`|Efekt yok (önişlemci tarafından kaldırıldı)|Efekt yok (önişlemci tarafından kaldırıldı)|`L`(aşağıdaki karakteri veya dizeyi Unicode muadili olarak dönüştürür)|

Yordamların, değişkenlerin ve diğer nesnelerin genel metin eşlemelerinin listesi için, Çalışma Zamanı Kitaplığı Başvurusu'ndaki [Genel Metin Eşlemeleri'ne](../c-runtime-library/generic-text-mappings.md) bakın.

> [!NOTE]
> Gömülü null `str` baytlar içerme olasılığı yüksek olan Unicode dizelerine sahip işlevler ailesini kullanmayın. Benzer şekilde, MBCS (veya SBCS) dizelerine sahip `wcs` işlevailesikullanmayın.

Aşağıdaki kod parçaları, MBCS, Unicode ve SBCS modellerinin `_TCHAR` kullanımını ve `_tcsrev` eşleme için kullanımını göstermektedir.

```cpp
_TCHAR *RetVal, *szString;
RetVal = _tcsrev(szString);
```

`_MBCS` Tanımlanmışsa, önişlemci bu parçayı bu kodla eşler:

```cpp
char *RetVal, *szString;
RetVal = _mbsrev(szString);
```

`_UNICODE` Tanımlanmışsa, önişlemci bu parçayı bu kodla eşler:

```cpp
wchar_t *RetVal, *szString;
RetVal = _wcsrev(szString);
```

Ne `_MBCS` değilse `_UNICODE` veya tanımlanmamışsa, önişlemci parçayı aşağıdaki gibi tek bayt ASCII koduyla eşler:

```cpp
char *RetVal, *szString;
RetVal = strrev(szString);
```

Bu nedenle, üç karakter kümesinden herhangi biri için özel yordamlarla çalışacak tek kaynakkodlu bir kod dosyası yazabilir, koruyabilir ve derleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Metin ve Dizeleri](../text/text-and-strings-in-visual-cpp.md)<br/>
[_MBCS Kodu ile TCHAR.H Veri Türlerini Kullanma](../text/using-tchar-h-data-types-with-mbcs-code.md)
