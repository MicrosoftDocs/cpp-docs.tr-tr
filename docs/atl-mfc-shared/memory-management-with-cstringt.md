---
title: Bellek yönetimi CStringT ile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringT
- ATL::CStringT
- ATL.CStringT
dev_langs:
- C++
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b65efd934fecdab36bfa1c0c882de1dd8862c81f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="memory-management-with-cstringt"></a>CStringT ile bellek yönetimi
Sınıf [CStringT](../atl-mfc-shared/reference/cstringt-class.md) değişken uzunlukta karakter dizeleri işlemek için kullanılan bir şablon sınıftır. Bu dizeler tutmak için bellek tahsis ve her örneği ile ilişkili bir dize Yöneticisi nesnesi aracılığıyla serbest `CStringT`. MFC ve ATL sağlamak varsayılan işlemlerinden `CStringT`adlı `CString`, `CStringA`, ve `CStringW`, farklı karakter türleri dizeleri işlemek. Bu karakter türlerini türlerinin **TCHAR**, `char`, ve `wchar_t`sırasıyla. Bu varsayılan dize türleri işlem yığınında (ATL) veya CRT yığınında (MFC) bellek ayırır bir dize Yöneticisi'ni kullanın. Tipik uygulamalar için bu bellek ayırma şeması yeterli olur. Ancak, yoğun yapmadan kodunu dizeleri (veya birden çok iş parçacıklı kodu) varsayılan bellek yöneticilerini en iyi şekilde çalışmayabilir kullanın. Bu konu, varsayılan bellek yönetimi davranışını geçersiz kılmak açıklar `CStringT`, elinizdeki için iyileştirilmiş allocators özellikle oluşturma.  
  
-   [Özel Dize Yöneticisi’ni Uygulama (Temel Yöntem)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)  
  
-   [Yığın Çekişmesini Engelleme](../atl-mfc-shared/avoidance-of-heap-contention.md)  
  
-   [Özel Dize Yöneticisi’ni Uygulama (Gelişmiş Yöntem)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)  
  
-   [CFixedStringT: Örnek bir özel dize Yöneticisi'nin](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CustomString örnek](../visual-cpp-samples.md)

