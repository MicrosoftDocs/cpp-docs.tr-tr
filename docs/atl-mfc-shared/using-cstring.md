---
title: CString kullanarak | Microsoft Docs
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
ms.openlocfilehash: 5759c8a0aaa628d612010cb7d04690a3d3bfa54f
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238727"
---
# <a name="using-cstring"></a>CString kullanma
Bu bölümdeki konular, ile programlamayı açıklamaktadır `CString`. Hakkında başvuru belgeleri için `CString` sınıfı, belgelerine bakın [CStringT](../atl-mfc-shared/reference/cstringt-class.md).  
  
 Kullanılacak `CString`, dahil `atlstr.h` üstbilgi.  
  
 `CString`, `CStringA`, Ve `CStringW` sınıflardır özelleştirmeleri adlı bir sınıf şablonu [CStringT](../atl-mfc-shared/reference/cstringt-class.md) destekledikleri karakter veri türüne göre.  
  
 A `CStringW` nesnesini içeren `wchar_t` yazın ve Unicode dizeleri destekler. A `CStringA` nesnesini içeren `char` türü ve destekleyen tek baytlı ve çok baytlı (MBCS) dizeleri. A `CString` nesnesi ya da destekler `char` türü veya `wchar_t` türüne mi bağlı `MBCS` simge veya `UNICODE` simgesi derleme zamanında tanımlanır.  
  
 A `CString` nesne karakter verileri tutar bir `CStringData` nesnesi. `CString` kabul `null`-C stilinde dizeleri sonlandırıldı. `CString` dize uzunluğu daha hızlı performans, ancak aynı zamanda korur parçaları `null` LPCWSTR dönüştürme desteklemek için depolanan karakter verilerinde karakter. `CString` bir C stili dize verdiğinde null Sonlandırıcı içerir. Ekleyebileceğiniz bir `null` başka konumlara bir `CString`, ancak beklenmeyen sonuçlara neden olabilir.  
  
 Aşağıdaki dize sınıfları kümesi ile veya CRT desteği olmadan bir MFC kitaplık bağlamadan kullanılabilir: `CAtlString`, `CAtlStringA`, ve `CAtlStringW`.  
  
 `CString` Yerel projelerinde kullanılır. Yönetilen kod için (C + +/ CLI) projeleri kullanmak `System::String`.  
  
 Daha fazla özellikler eklemek için `CString`, `CStringA`, veya `CStringW` şu anda sunar, bir alt sınıfı, oluşturduğunuz `CStringT` ek özellikler içerir.  
  
 Aşağıdaki kodu nasıl oluşturulacağını gösterir bir `CString` ve bunu standart çıktıya yazdırma:  
  
```cpp  
#include <atlstr.h>  
  
int main() {  
    CString aCString = CString(_T("A string"));  
    _tprintf(_T("%s"), (LPCTSTR) aCString);  
}  
```  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Temel CString İşlemleri](../atl-mfc-shared/basic-cstring-operations.md)  
 Temel açıklar `CString` işlemleri, tek tek karakter erişme C değişmez değer dizeleri nesneleri oluşturma dahil olmak üzere bir `CString`, iki nesne birleştirme ve karşılaştırma `CString` nesneleri.  
  
 [Dize Veri Yönetimi](../atl-mfc-shared/string-data-management.md)  
 Unicode ve MBCS ile kullanarak ele `CString`.  
  
 [CString Semantiği](../atl-mfc-shared/cstring-semantics.md)  
 Açıklar nasıl `CString` nesnesi kullanılır.  
  
 [C Stili Dizelerle İlgili CString İşlemleri](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)  
 İçeriğini düzenleme açıklayan bir `CString` nesne C türü null sonlandırılmış bir dize gibi.  
  
 [BSTR için Bellek Ayırma ve Serbest Bırakma](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)  
 İçin bellek kullanımını açıklar bir `BSTR` ve COM nesneleri.  
  
 [CString Özel Durum Temizleme](../atl-mfc-shared/cstring-exception-cleanup.md)  
 Bu açık temizleme MFC 3.0 açıklar ve daha sonra artık gerekli değildir.  
  
 [CString Bağımsız Değişken Geçirme](../atl-mfc-shared/cstring-argument-passing.md)  
 İşlevler CString nesneleri geçirmek nasıl ve nasıl döndürüleceğini açıklamaktadır `CString` işlevleri nesneleri.  
  
 [Unicode ve Çok Baytlı Karakter Kümesi (MBCS) Desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)  
 MFC Unicode için etkindir ve MBCS desteği nasıl ele alınmaktadır.  
  
## <a name="reference"></a>Başvuru  
 [CStringT](../atl-mfc-shared/reference/cstringt-class.md)  
 Hakkında başvuru bilgileri sağlar `CStringT` sınıfı.  
  
 [CSimpleStringT Sınıfı](../atl-mfc-shared/reference/csimplestringt-class.md)  
 Hakkında başvuru bilgileri sağlar `CSimpleStringT` sınıfı.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)  
 Dize verilerini yönetmek için birkaç yöntem açıklayan konulara bağlantılar içerir.  
  
 [Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

