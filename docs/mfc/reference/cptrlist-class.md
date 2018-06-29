---
title: CPtrList sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPtrList
dev_langs:
- C++
helpviewer_keywords:
- lists, generic
- CPtrList class [MFC]
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 421373969beb83d033ce8ca14bd11fdb5d8dcb14
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078627"
---
# <a name="cptrlist-class"></a>CPtrList sınıfı
Void işaretçileri listesini destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPtrList : public CObject  
```  
  
## <a name="members"></a>Üyeler  
 Üye işlevlerini `CPtrList` sınıfının üye fonksiyonları benzer [CObList](../../mfc/reference/coblist-class.md). Bu benzerlik nedeniyle kullandığınız `CObList` başvuru belgelerini üye fonksiyonu özellikleri için. Gördüğünüz yerde bir `CObject` işaretçisi bir işlev parametresi veya dönüş değeri olarak değiştirmek için bir işaretçi **void**.  
  
 `CObject*& CObList::GetHead() const;`  
  
 Örneğin, çevrilir  
  
 `void*& CPtrList::GetHead() const;`  
  
## <a name="remarks"></a>Açıklamalar  
 `CPtrList` bir araya getirir `IMPLEMENT_DYNAMIC` çalışma zamanı tür erişimi ve için dökme desteklemek için makrosu bir `CDumpContext` nesnesi. Tek tek işaretçi liste öğelerini, bir dökümü gerekiyorsa, 1 veya daha büyük döküm bağlam derinliği ayarlamanız gerekir.  
  
 İşaretçi listeleri seri hale getirilemez.  
  
 Zaman bir `CPtrList` Nesne silindiğinden veya öğeleri kaldırıldığında, yalnızca işaretçileri kaldırılır, yok oldukları varlıklar.  
  
 Kullanma hakkında daha fazla bilgi için `CPtrList`, makaleye bakın [koleksiyonları](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CPtrList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcoll.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CObList Sınıfı](../../mfc/reference/coblist-class.md)
