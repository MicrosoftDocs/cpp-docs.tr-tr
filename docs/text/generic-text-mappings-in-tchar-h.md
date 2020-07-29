---
title: Tchar. h 'de Genel metin eşlemeleri
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
ms.openlocfilehash: c317e7d67cc3d086dacbe0f24b0103d389afefda
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217304"
---
# <a name="generic-text-mappings-in-tcharh"></a>Tchar. h 'de Genel metin eşlemeleri

Uluslararası kullanım için kodun taşınmasını basitleştirmek amacıyla, Microsoft çalışma zamanı kitaplığı birçok veri türü, yordamlar ve diğer nesneler için Microsoft 'a özgü genel metin eşlemeleri sağlar. Bir bildirimini kullanarak tanımladığınız bir bildirim sabitine bağlı olarak, tek baytlı, çok baytlı veya Unicode karakter kümeleri için derlenebilecek genel kod yazmak üzere Tchar. h içinde tanımlanan bu eşlemeleri kullanabilirsiniz `#define` . Genel metin eşlemeleri, ANSI uyumlu olmayan Microsoft uzantılarıdır.

Tchar. h kullanarak, aynı kaynaklardan tek baytlı, çok baytlı karakter kümesi (MBCS) ve Unicode uygulamaları oluşturabilirsiniz. Tchar. h, doğru önişlemci tanımlarına sahip olan makroları (öneki olan) tanımlar,, `_tcs` `str` `_mbs` veya `wcs` işlevlerine uygun şekilde eşleyin. MBCS oluşturmak için, sembolünü tanımlayın `_MBCS` . Unicode oluşturmak için simgeyi tanımlayın `_UNICODE` . Tek baytlık bir uygulama oluşturmak için, (varsayılan) öğesini değil tanımlayın. Varsayılan olarak `_UNICODE` MFC uygulamaları için tanımlanmıştır.

`_TCHAR`Veri türü Tchar. h içinde koşullu olarak tanımlanır. Sembol `_UNICODE` derleme için tanımlıysa, `_TCHAR` olarak tanımlanır **`wchar_t`** ; Aksi takdirde, tek baytlı ve MBCS derlemeleri için olarak tanımlanır **`char`** . ( **`wchar_t`** basit Unicode geniş karakterli veri türü, 8 bit 'e karşılık gelen 16 bittir **`signed char`** .) Uluslararası uygulamalar için, `_tcs` bayt değil birimlerde çalışan işlev ailesini kullanın `_TCHAR` . Örneğin, `_tcsncpy` `n` `_TCHARs` bayt değil, kopyalar `n` .

Bazı tek bayt karakter kümesi (SBCS) dize işleme işlevleri (imzalı) parametre aldığı için **`char*`** , tanımlandığında bir tür uyuşmazlığı derleyici uyarısı oluşur `_MBCS` . Bu uyarıyı önlemenin üç yolu vardır:

1. Tchar. h içinde tür kullanımı uyumlu satır içi işlev dönüştürücüler kullanın. Bu, varsayılan davranıştır.

1. Komut satırını tanımlayarak Tchar. h içindeki doğrudan makroları kullanın `_MB_MAP_DIRECT` . Bunu yaparsanız, türleri el ile eşleştirebilirsiniz. Bu en hızlı yöntemdir, ancak tür kullanımı güvenli değildir.

1. Tchar. h içinde tür kullanımı uyumlu statik bağlantılı kitaplık işlevi dönüştürücüler kullanın. Bunu yapmak için, `_NO_INLINING` komut satırında sabiti tanımlayın. Bu en yavaş yöntemdir, ancak tür açısından güvenlidir.

### <a name="preprocessor-directives-for-generic-text-mappings"></a>Genel metin eşlemeleri için Önişlemci yönergeleri

|# define|Derlenmiş sürüm|Örnek|
|---------------|----------------------|-------------|
|`_UNICODE`|Unicode (geniş karakter)|`_tcsrev`eşleme`_wcsrev`|
|`_MBCS`|Çok baytlı karakter|`_tcsrev`eşleme`_mbsrev`|
|Hiçbiri (varsayılan değer `_UNICODE` veya tanımlı değil `_MBCS` )|SBCS (ASCıı)|`_tcsrev`eşleme`strrev`|

Örneğin, `_tcsrev` Tchar. h 'de tanımlanan genel metin işlevi, `_mbsrev` `_MBCS` programınızda tanımladıysanız veya ' i `_wcsrev` tanımlıysa ile eşlenir `_UNICODE` . Aksi takdirde, `_tcsrev` ile eşlenir `strrev` . Diğer veri türü eşlemeleri, programlama kolaylığı için Tchar. h içinde sağlanır, ancak `_TCHAR` en yararlı seçenektir.

### <a name="generic-text-data-type-mappings"></a>Genel metin veri türü eşlemeleri

|Genel metin<br /> Veri türü adı|_UNICODE &<br /> _MBCS tanımsız|_MBCS<br /> Tanımlı|_UNICODE<br /> Tanımlı|
|--------------------------------------|----------------------------------------|------------------------|---------------------------|
|`_TCHAR`|**`char`**|**`char`**|**`wchar_t`**|
|`_TINT`|**`int`**|**`unsigned int`**|`wint_t`|
|`_TSCHAR`|**`signed char`**|**`signed char`**|**`wchar_t`**|
|`_TUCHAR`|**`unsigned char`**|**`unsigned char`**|**`wchar_t`**|
|`_TXCHAR`|**`char`**|**`unsigned char`**|**`wchar_t`**|
|`_T` veya `_TEXT`|Efekt yok (ön işlemci tarafından kaldırıldı)|Efekt yok (ön işlemci tarafından kaldırıldı)|`L`(aşağıdaki karakteri veya dizeyi Unicode karşılığına dönüştürür)|

Yordamların, değişkenlerin ve diğer nesnelerin genel metin eşlemelerinin bir listesi için bkz. çalışma zamanı kitaplık başvurusunda [Genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md) .

> [!NOTE]
> `str`İşlev ailesini, gömülü null baytları içermesi olası Unicode dizeleriyle birlikte kullanmayın. Benzer şekilde, `wcs` MBCS (veya SBCS) dizeleriyle birlikte işlev ailesini kullanmayın.

Aşağıdaki kod parçaları `_TCHAR` `_tcsrev` MBCS, UNICODE ve SBCS modellerine eşleme için ve kullanımını gösterir.

```cpp
_TCHAR *RetVal, *szString;
RetVal = _tcsrev(szString);
```

`_MBCS`Tanımlanmışsa, Önişlemci bu parçayı bu kodla eşler:

```cpp
char *RetVal, *szString;
RetVal = _mbsrev(szString);
```

`_UNICODE`Tanımlanmışsa, Önişlemci bu parçayı bu kodla eşler:

```cpp
wchar_t *RetVal, *szString;
RetVal = _wcsrev(szString);
```

Ne `_MBCS` de `_UNICODE` tanımlı değilse, ön işlemci parçayı şu şekilde tek baytlı ASCII koduna eşler:

```cpp
char *RetVal, *szString;
RetVal = strrev(szString);
```

Bu nedenle, üç tür karakter kümesinden birine özgü yordamlar ile çalışmak için tek kaynaklı bir kod dosyası yazabilir, bakımını yapabilir ve derleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Metin ve dizeler](../text/text-and-strings-in-visual-cpp.md)<br/>
[TCHAR kullanma. _MBCS kodlu H veri türleri](../text/using-tchar-h-data-types-with-mbcs-code.md)
