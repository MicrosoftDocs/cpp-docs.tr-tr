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
ms.openlocfilehash: af042c80b9e3e0de872261f89255a26728b218cd
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440506"
---
# <a name="memory-management-with-cstringt"></a>CStringT ile bellek yönetimi

[CStringT](../atl-mfc-shared/reference/cstringt-class.md) sınıfı, değişken uzunluklu karakter dizelerini işlemek için kullanılan bir şablon sınıfıdır. Bu dizeleri tutacak bellek, her bir `CStringT`örneğiyle ilişkili bir String Manager nesnesi aracılığıyla ayrılır ve serbest bırakılır. MFC ve ATL, farklı karakter türlerindeki dizeleri işleyen `CString`, `CStringA`ve `CStringW`olarak adlandırılan varsayılan `CStringT`örneklemesini sağlar. Bu karakter türleri sırasıyla TCHAR, **char**ve `wchar_t`türündedir. Bu varsayılan dize türleri, işlem yığınından (ATL 'de) veya CRT yığında (MFC 'de) bellek ayıran bir String Manager kullanır. Tipik uygulamalar için bu bellek ayırma şeması yeterlidir. Ancak, dizeler (veya çok iş parçacıklı kod) yoğun bir şekilde kullanmasını sağlamak için varsayılan bellek yöneticileri en iyi şekilde gerçekleştirilemeyebilir. Bu konu, `CStringT`varsayılan bellek yönetimi davranışının nasıl geçersiz kılınacağını, tek seferde görev için özel olarak iyileştirilmiş ayrıcılar oluşturmayı açıklar.

- [Özel Dize Yöneticisi’ni Uygulama (Temel Yöntem)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)

- [Yığın Çekişmesini Engelleme](../atl-mfc-shared/avoidance-of-heap-contention.md)

- [Özel Dize Yöneticisi’ni Uygulama (Gelişmiş Yöntem)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)

- [CFixedStringT: özel bir dize Yöneticisi örneği](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)

## <a name="see-also"></a>Ayrıca bkz.

[CustomString örneği](../overview/visual-cpp-samples.md)
