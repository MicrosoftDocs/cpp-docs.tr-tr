---
title: CStringT ile bellek yönetimi
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
ms.openlocfilehash: bf1f99b92761c84d59b6f7bfb9aef67d7e097893
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222036"
---
# <a name="memory-management-with-cstringt"></a>CStringT ile bellek yönetimi

[CStringT](../atl-mfc-shared/reference/cstringt-class.md) sınıfı, değişken uzunluklu karakter dizelerini işlemek için kullanılan bir şablon sınıfıdır. Bu dizeleri tutacak bellek, her bir örneğiyle ilişkili bir String Manager nesnesi aracılığıyla ayrılır ve serbest bırakılır `CStringT` . MFC ve ATL, `CStringT` `CString` `CStringA` `CStringW` farklı karakter türlerindeki dizeleri düzenleyen,, ve olarak adlandırılan varsayılan örneklemeleri sağlar. Bu karakter türleri sırasıyla TCHAR, **`char`** , ve, türündedir **`wchar_t`** . Bu varsayılan dize türleri, işlem yığınından (ATL 'de) veya CRT yığında (MFC 'de) bellek ayıran bir String Manager kullanır. Tipik uygulamalar için bu bellek ayırma şeması yeterlidir. Ancak, dizeler (veya çok iş parçacıklı kod) yoğun bir şekilde kullanmasını sağlamak için varsayılan bellek yöneticileri en iyi şekilde gerçekleştirilemeyebilir. Bu konu, ' nin varsayılan bellek yönetimi davranışının nasıl geçersiz kılınacağını `CStringT` , el ile yapılan görev için özel olarak iyileştirilmiş ayrılıcılar oluşturmayı açıklar.

- [Özel bir dize Yöneticisi (temel yöntem) uygulama](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)

- [Engelleme yığın çakışması](../atl-mfc-shared/avoidance-of-heap-contention.md)

- [Özel bir dize Yöneticisi (Gelişmiş Yöntem) uygulama](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)

- [CFixedStringT: özel bir dize Yöneticisi örneği](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)

## <a name="see-also"></a>Ayrıca bkz.

[CustomString örneği](../overview/visual-cpp-samples.md)
