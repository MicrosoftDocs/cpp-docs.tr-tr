---
title: CStringT ile bellek yönetimi
ms.date: 11/04/2016
f1_keywords:
- CStringT
- ATL::CStringT
- ATL.CStringT
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
ms.openlocfilehash: f45aac11f0c42aecf8c72cf6f7d1630d50b780f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598031"
---
# <a name="memory-management-with-cstringt"></a>CStringT ile bellek yönetimi

Sınıf [CStringT](../atl-mfc-shared/reference/cstringt-class.md) değişken uzunlukta karakter dizeleri işlemek için kullanılan bir şablon sınıfı. Bu dizeler tutmak için bellek tahsis ve her örneği ile ilişkili bir dize Yöneticisi nesnesi aracılığıyla yayımlanan `CStringT`. MFC ve ATL sağlayan varsayılan örneklemeleri `CStringT`adlı `CString`, `CStringA`, ve `CStringW`, farklı karakter türlerinin dizeleri işleme. Bu karakter türlerini TCHAR, türlerinin **char**, ve `wchar_t`sırasıyla. Bu varsayılan dize türleri (ATL), işlem yığınını ya da CRT yığınında (MFC) bellek ayırır. bir dize Yöneticisi'ni kullanın. Tipik uygulamalarda, bu bellek ayırma düzeni yeterli olur. Ancak, dizeleri (veya birden çok iş parçacıklı kod) varsayılan bellek yöneticilerini en uygun şekilde çalışmayabilir yoğun yapmadan kodunu kullanın. Bu konuda varsayılan bellek yönetimi davranışını geçersiz kılmayı açıklar `CStringT`, iyileştirilmiş elinizdeki için ayırıcılar özellikle oluşturma.

- [Özel Dize Yöneticisi’ni Uygulama (Temel Yöntem)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)

- [Yığın Çekişmesini Engelleme](../atl-mfc-shared/avoidance-of-heap-contention.md)

- [Özel Dize Yöneticisi’ni Uygulama (Gelişmiş Yöntem)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)

- [CFixedStringT: Örnek özel dize Yöneticisi](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)

## <a name="see-also"></a>Ayrıca Bkz.

[CustomString örnek](../visual-cpp-samples.md)

