---
title: "CPtrList sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7e69c8c0d80fea2720ea436bf0bff796ae57a60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cptrlist-class"></a>CPtrList sınıfı
Void işaretçileri listesini destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPtrList : public CObject  
```  
  
## <a name="members"></a>Üyeler  
 Üye işlevlerini `CPtrList` sınıfının üye fonksiyonları benzer [CObList](../../mfc/reference/coblist-class.md). Bu benzerlik nedeniyle kullandığınız `CObList` başvuru belgelerini üye fonksiyonu özellikleri için. Gördüğünüz yerde bir `CObject` işaretçisi bir işlev parametresi veya dönüş değeri olarak değiştirmek için bir işaretçi `void`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 Örneğin, çevrilir  
  
 `void*& CPtrList::GetHead() const;`  
  
## <a name="remarks"></a>Açıklamalar  
 `CPtrList`bir araya getirir `IMPLEMENT_DYNAMIC` çalışma zamanı tür erişimi ve için dökme desteklemek için makrosu bir `CDumpContext` nesnesi. Tek tek işaretçi liste öğelerini, bir dökümü gerekiyorsa, 1 veya daha büyük döküm bağlam derinliği ayarlamanız gerekir.  
  
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
