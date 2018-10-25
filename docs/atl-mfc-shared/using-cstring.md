---
title: CString kullanma | Microsoft Docs
ms.custom: ''
ms.date: 06/18/2018
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CString objects, C++ string manipulation
- CString objects, reference counting
- CString class (Visual C++)
ms.assetid: ed018aaf-8b10-46f9-828c-f9c092dc7609
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45c1c105fafcadab74107b008f437d49f420e66e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061098"
---
# <a name="using-cstring"></a>CString kullanma

Bu bölümdeki konular ile programlamayı açıklar `CString`. Hakkındaki referans belgeleri `CString` sınıfı, belgelerine bakın [CStringT](../atl-mfc-shared/reference/cstringt-class.md).

Kullanılacak `CString`, dahil `atlstr.h` başlığı.

`CString`, `CStringA`, Ve `CStringW` sınıflardır adlı bir sınıf şablonunun uzmanlıkları [CStringT](../atl-mfc-shared/reference/cstringt-class.md) destekledikleri karakter veri türüne göre.

A `CStringW` nesnesini içeren **wchar_t** yazın ve Unicode dizelerini destekler. A `CStringA` nesnesini içeren **char** türü ve destekleyen tek baytlı ve çok baytlı (MBCS) dizeleri. A `CString` nesnesi ya da destekler **char** türü veya `wchar_t` MBCS sembol veya UNICODE sembolü derleme zamanında tanımlı olup olmadığı bağlı olarak türü.

A `CString` nesnesi karakter verileri tutan bir `CStringData` nesne. `CString` NULL ile sonlandırılmış C stili dizeler kabul eder. `CString` dize izler ancak daha hızlı performans için uzunluk LPCWSTR dönüştürmeyi desteklemek için depolanan karakter verileri NULL karakter de korur. `CString` C stili dize verdiğinde null Sonlandırıcı içerir. İçinde başka yerlerde bir NULL ekleyebilirsiniz bir `CString`, ancak beklenmeyen sonuçlara neden olabilir.

Aşağıdaki dize sınıfları kümesi ile ya da CRT desteği olmadan, bir MFC Kitaplığı bağlama olmadan kullanılabilir: `CAtlString`, `CAtlStringA`, ve `CAtlStringW`.

`CString` Yerel projelerinde kullanılır. Yönetilen kod için (C + +/ CLI) projeleri kullanmak `System::String`.

Daha fazla özellik eklemek için `CString`, `CStringA`, veya `CStringW` şu anda sunar, öğesinin oluşturduğunuz `CStringT` , ek özellikleri içerir.

Aşağıdaki kod nasıl oluşturulacağını gösterir. bir `CString` ve bunu standart çıktıya yazdırın:

```cpp
#include <atlstr.h>

int main() {
    CString aCString = CString(_T("A string"));
    _tprintf(_T("%s"), (LPCTSTR) aCString);
}
```

## <a name="in-this-section"></a>Bu Bölümde

[Temel CString İşlemleri](../atl-mfc-shared/basic-cstring-operations.md)<br/>
Temel açıklar `CString` işlemleri, tek karakterler erişme C değişmez değer dizeleri nesneleri oluşturma da dahil olmak üzere bir `CString`, iki nesne birleştirme ve karşılaştırma `CString` nesneleri.

[Dize Veri Yönetimi](../atl-mfc-shared/string-data-management.md)<br/>
Unicode ve MBCS ile kullanımını açıklar `CString`.

[CString Semantiği](../atl-mfc-shared/cstring-semantics.md)<br/>
Açıklayan nasıl `CString` nesnesi kullanılır.

[C Stili Dizelerle İlgili CString İşlemleri](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)<br/>
Düzenleme içeriğini açıklayan bir `CString` nesne gibi bir C tarzı null ile sonlandırılmış dize.

[BSTR için Bellek Ayırma ve Serbest Bırakma](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)<br/>
BSTR ve COM nesneleri için bellek kullanımını açıklar.

[CString Özel Durum Temizleme](../atl-mfc-shared/cstring-exception-cleanup.md)<br/>
Bu açıkça temizlenmesi MFC 3.0 açıklar ve daha sonra artık gerekli değildir.

[CString Bağımsız Değişken Geçirme](../atl-mfc-shared/cstring-argument-passing.md)<br/>
CString nesneleri işlevlere geçirmek nasıl ve nasıl döndürüleceğini açıklar `CString` işlevleri nesneleri.

[Unicode ve Çok Baytlı Karakter Kümesi (MBCS) Desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)<br/>
MFC için Unicode etkinleştirilir ve MBCS desteği nasıl açıklar.

## <a name="reference"></a>Başvuru

[CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
Hakkında başvuru bilgileri sağlar `CStringT` sınıfı.

[CSimpleStringT Sınıfı](../atl-mfc-shared/reference/csimplestringt-class.md)<br/>
Hakkında başvuru bilgileri sağlar `CSimpleStringT` sınıfı.

## <a name="related-sections"></a>İlgili Bölümler

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
Dize verileri yönetmek için çeşitli yollar açıklayan konulara bağlantılar içerir.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

