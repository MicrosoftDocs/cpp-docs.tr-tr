---
title: "Bellek yönetimi CStringT ile | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringT
- ATL::CStringT
- ATL.CStringT
dev_langs: C++
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5f36e27a536ce8983baaca594b5768479b16a74d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="memory-management-with-cstringt"></a>CStringT ile bellek yönetimi
Sınıf [CStringT](../atl-mfc-shared/reference/cstringt-class.md) değişken uzunlukta karakter dizeleri işlemek için kullanılan bir şablon sınıftır. Bu dizeler tutmak için bellek tahsis ve her örneği ile ilişkili bir dize Yöneticisi nesnesi aracılığıyla serbest `CStringT`. MFC ve ATL sağlamak varsayılan işlemlerinden `CStringT`adlı `CString`, `CStringA`, ve `CStringW`, farklı karakter türleri dizeleri işlemek. Bu karakter türlerini türlerinin **TCHAR**, `char`, ve `wchar_t`sırasıyla. Bu varsayılan dize türleri işlem yığınında (ATL) veya CRT yığınında (MFC) bellek ayırır bir dize Yöneticisi'ni kullanın. Tipik uygulamalar için bu bellek ayırma şeması yeterli olur. Ancak, yoğun yapmadan kodunu dizeleri (veya birden çok iş parçacıklı kodu) varsayılan bellek yöneticilerini en iyi şekilde çalışmayabilir kullanın. Bu konu, varsayılan bellek yönetimi davranışını geçersiz kılmak açıklar `CStringT`, elinizdeki için iyileştirilmiş allocators özellikle oluşturma.  
  
-   [Uygulama bir özel dize Yöneticisi'nin (temel yöntemi)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)  
  
-   [Yığın Çekişme kaçınma](../atl-mfc-shared/avoidance-of-heap-contention.md)  
  
-   [Uygulama bir özel dize Yöneticisi'nin (Gelişmiş yöntemi)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)  
  
-   [CFixedStringT: Örnek bir özel dize Yöneticisi'nin](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CustomString örnek](../visual-cpp-samples.md)

