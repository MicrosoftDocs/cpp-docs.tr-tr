---
title: "CDocItem sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
dev_langs: C++
helpviewer_keywords:
- CDocItem [MFC], GetDocument
- CDocItem [MFC], IsBlank
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a4987554965674612eaf8d9aa78c659f7f28b75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdocitem-class"></a>CDocItem sınıfı
Bir belgenin veri bileşenleridir belge öğeleri için temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDocItem : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocItem::GetDocument](#getdocument)|Öğeyi içeren belgeyi döndürür.|  
|[CDocItem::IsBlank](#isblank)|Öğe bilgileri içerip içermediğini belirler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDocItem`nesneleri, istemci ve sunucu belgelerde OLE öğeleri göstermek için kullanılır.  
  
 Daha fazla bilgi için bkz: [kapsayıcıları: bir kapsayıcı uygulama](../../mfc/containers-implementing-a-container.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocItem`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="getdocument"></a>CDocItem::GetDocument  
 Öğeyi içeren belge almak için bu işlevini çağırın.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeyi içeren belge için bir işaretçi; **NULL**öğesi belgenin bir bölümünü değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev türetilmiş sınıflarda kılınmadığı [COleClientItem](../../mfc/reference/coleclientitem-class.md) ve [COleServerItem](../../mfc/reference/coleserveritem-class.md), ya da bir işaretçi döndüren bir [COleDocument](../../mfc/reference/coledocument-class.md), [ COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), veya bir [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) nesnesi.  
  
##  <a name="isblank"></a>CDocItem::IsBlank  
 Varsayılan serileştirme oluştuğunda çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hiçbir bilgi öğesi içeriyorsa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `CDocItem` nesneler boş değildir. [COleClientItem](../../mfc/reference/coleclientitem-class.md) nesneleri bazen boş bunlar doğrudan öğesinden türetilen çünkü `CDocItem`. Ancak, [COleServerItem](../../mfc/reference/coleserveritem-class.md) nesneleri boş her zaman. Varsayılan olarak, içeren OLE uygulamalar `COleClientItem` hiçbir x veya y sahip nesneleri ölçüde serileştirilir. Bu döndürerek yapılır **TRUE** geçersiz kılma gelen `IsBlank` hiçbir x veya y öğe olduğunda kapsam.  
  
 Seri hale getirme sırasında diğer eylemleri uygulamak istiyorsanız, bu işlev geçersiz kılar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDocument sınıfı](../../mfc/reference/coledocument-class.md)   
 [COleServerItem sınıfı](../../mfc/reference/coleserveritem-class.md)   
 [COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)
