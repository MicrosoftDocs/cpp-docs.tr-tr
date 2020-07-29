---
title: CString kullanma
ms.date: 06/18/2018
helpviewer_keywords:
- CString objects, C++ string manipulation
- CString objects, reference counting
- CString class (Visual C++)
ms.assetid: ed018aaf-8b10-46f9-828c-f9c092dc7609
ms.openlocfilehash: 8ebf3441c7d8856fe412e2efed4c717b01ced362
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219020"
---
# <a name="using-cstring"></a>CString kullanma

Bu bölümdeki konular ile nasıl programlama yapılacağını açıklamaktadır `CString` . Sınıfıyla ilgili başvuru belgeleri için `CString` bkz. [CStringT](../atl-mfc-shared/reference/cstringt-class.md)belgeleri.

Kullanmak için `CString` `atlstr.h` üst bilgiyi ekleyin.

`CString`, `CStringA` , Ve `CStringW` sınıfları, destekledikleri karakter verilerinin türüne göre [CStringT](../atl-mfc-shared/reference/cstringt-class.md) adlı bir sınıf şablonunun uzmanlıklarıdır.

Bir `CStringW` nesne türü içerir **`wchar_t`** ve Unicode dizelerini destekler. Bir `CStringA` nesne türü içerir **`char`** ve tek baytlı ve çok BAYTLı (MBCS) dizeleri destekler. Bir `CString` nesne, **`char`** **`wchar_t`** MBCS SEMBOLÜNÜN mi yoksa UNICODE sembolünün derleme zamanında mi tanımlandığına bağlı olarak türü ya da türü destekler.

`CString`Nesne, bir nesnede karakter verilerini tutar `CStringData` . `CString`NULL ile sonlandırılmış C stili dizeleri kabul eder. `CString`daha hızlı performans için dize uzunluğunu izler, ancak LPCWSTR 'e dönüştürmeyi desteklemek için depolanan karakter verilerinde NULL karakteri de korur. `CString`, bir C stili dize dışarı aktardığında null Sonlandırıcı içerir. Başka konumlarda bir NULL ekleyebilirsiniz `CString` , ancak bu durum beklenmedik sonuçlara neden olabilir.

Aşağıdaki dize sınıfları kümesi, CRT desteği olan veya olmayan bir MFC Kitaplığı bağlamadan kullanılabilir: `CAtlString` , `CAtlStringA` ve `CAtlStringW` .

`CString`Yerel projelerde kullanılır. Yönetilen kod (C++/CLı) projeleri için kullanın `System::String` .

, Veya şu anda tekliften daha fazla özellik eklemek için `CString` `CStringA` `CStringW` , ek özellikleri içeren bir alt sınıfı oluşturmalısınız `CStringT` .

Aşağıdaki kod, oluşturma `CString` ve standart çıktıya yazdırma işlemlerinin nasıl yapılacağını gösterir:

```cpp
#include <atlstr.h>

int main() {
    CString aCString = CString(_T("A string"));
    _tprintf(_T("%s"), (LPCTSTR) aCString);
}
```

## <a name="in-this-section"></a>Bu Bölümde

[Temel CString Işlemleri](../atl-mfc-shared/basic-cstring-operations.md)<br/>
`CString`C değişmez dizelerinden nesne oluşturma, bir uygulamasındaki tek tek karakterlere erişme, `CString` iki nesneyi birleştirerek ve nesneleri karşılaştırma dahil olmak üzere temel işlemleri açıklar `CString` .

[Dize Veri Yönetimi](../atl-mfc-shared/string-data-management.md)<br/>
İle Unicode ve MBCS kullanımını açıklar `CString` .

[CString semantiği](../atl-mfc-shared/cstring-semantics.md)<br/>
Nesnelerin nasıl `CString` kullanıldığını açıklar.

[C stili dizeleriyle Ilgili CString Işlemleri](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)<br/>
Bir `CString` nesnenin Içeriğini C stili null ile sonlandırılmış bir dize gibi düzenleme işlemini açıklar.

[BSTR için bellek ayırma ve serbest bırakma](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)<br/>
BSTR ve COM nesneleri için bellek kullanımını açıklar.

[CString özel durum Temizleme](../atl-mfc-shared/cstring-exception-cleanup.md)<br/>
MFC 3,0 ve sonrasında açık Temizleme işleminin artık gerekli olmadığını açıklar.

[CString bağımsız değişken geçirme](../atl-mfc-shared/cstring-argument-passing.md)<br/>
CString nesnelerinin işlevlere nasıl geçirileceğini ve işlevlerden nesnelerin nasıl döneceğinizi açıklar `CString` .

[Unicode ve çok baytlı karakter kümesi (MBCS) desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)<br/>
MFC 'nin Unicode ve MBCS desteği için nasıl etkinleştirildiğini açıklar.

## <a name="reference"></a>Başvuru

[CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
Sınıfı hakkında başvuru bilgileri sağlar `CStringT` .

[CSimpleStringT sınıfı](../atl-mfc-shared/reference/csimplestringt-class.md)<br/>
Sınıfı hakkında başvuru bilgileri sağlar `CSimpleStringT` .

## <a name="related-sections"></a>İlgili Bölümler

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
Dize verilerini yönetmenin çeşitli yollarını tanımlayan konuların bağlantılarını içerir.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
