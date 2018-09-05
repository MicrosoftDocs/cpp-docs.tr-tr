---
title: CStringT ile bellek yönetimi | Microsoft Docs
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
ms.openlocfilehash: 8676626c47471c2d1702d49df3069b618cc3ff4f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752212"
---
# <a name="memory-management-with-cstringt"></a>CStringT ile bellek yönetimi

Sınıf [CStringT](../atl-mfc-shared/reference/cstringt-class.md) değişken uzunlukta karakter dizeleri işlemek için kullanılan bir şablon sınıfı. Bu dizeler tutmak için bellek tahsis ve her örneği ile ilişkili bir dize Yöneticisi nesnesi aracılığıyla yayımlanan `CStringT`. MFC ve ATL sağlayan varsayılan örneklemeleri `CStringT`adlı `CString`, `CStringA`, ve `CStringW`, farklı karakter türlerinin dizeleri işleme. Bu karakter türlerini TCHAR, türlerinin **char**, ve `wchar_t`sırasıyla. Bu varsayılan dize türleri (ATL), işlem yığınını ya da CRT yığınında (MFC) bellek ayırır. bir dize Yöneticisi'ni kullanın. Tipik uygulamalarda, bu bellek ayırma düzeni yeterli olur. Ancak, dizeleri (veya birden çok iş parçacıklı kod) varsayılan bellek yöneticilerini en uygun şekilde çalışmayabilir yoğun yapmadan kodunu kullanın. Bu konuda varsayılan bellek yönetimi davranışını geçersiz kılmayı açıklar `CStringT`, iyileştirilmiş elinizdeki için ayırıcılar özellikle oluşturma.

- [Özel Dize Yöneticisi’ni Uygulama (Temel Yöntem)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)

- [Yığın Çekişmesini Engelleme](../atl-mfc-shared/avoidance-of-heap-contention.md)

- [Özel Dize Yöneticisi’ni Uygulama (Gelişmiş Yöntem)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)

- [CFixedStringT: Örnek özel dize Yöneticisi](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)

## <a name="see-also"></a>Ayrıca Bkz.

[CustomString örnek](../visual-cpp-samples.md)

