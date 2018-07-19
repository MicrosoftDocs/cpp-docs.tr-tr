---
title: Cdocıtem sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
dev_langs:
- C++
helpviewer_keywords:
- CDocItem [MFC], GetDocument
- CDocItem [MFC], IsBlank
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88c30418f886cd791a7119367c5ddbccc19003fa
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335587"
---
# <a name="cdocitem-class"></a>Cdocıtem sınıfı
Bir belgenin verilerinin bileşenleri olan belge öğeleri için temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDocItem : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocItem::GetDocument](#getdocument)|Öğeyi içeren belge döndürür.|  
|[CDocItem::IsBlank](#isblank)|Öğe bilgileri içerip içermediğini belirler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDocItem` nesneler, istemci ve sunucu belgelerde OLE öğeleri göstermek için kullanılır.  
  
 Daha fazla bilgi için bkz [kapsayıcıları: bir kapsayıcı uygulama](../../mfc/containers-implementing-a-container.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocItem`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="getdocument"></a>  CDocItem::GetDocument  
 Öğeyi içeren belge almak için bu işlevi çağırın.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeyi içeren belge için bir işaretçi; Bir belge bir parçası değilse NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, türetilmiş sınıflarda kılınır [Coleclientıtem](../../mfc/reference/coleclientitem-class.md) ve [Coleserverıtem](../../mfc/reference/coleserveritem-class.md), ya da bir işaretçi döndüren bir [COleDocument](../../mfc/reference/coledocument-class.md), [ COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), veya bir [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) nesne.  
  
##  <a name="isblank"></a>  CDocItem::IsBlank  
 Varsayılan serileştirme oluştuğunda framework tarafından çağırılır.  
  
```  
virtual BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeyi içeren hiçbir bilgi olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `CDocItem` nesneler boş değildir. [Coleclientıtem](../../mfc/reference/coleclientitem-class.md) nesneleri bazen boş olduğundan, bunlar doğrudan öğesinden türetilen `CDocItem`. Ancak, [Coleserverıtem](../../mfc/reference/coleserveritem-class.md) nesnelerdir her zaman boş. Varsayılan olarak, OLE uygulamaları içeren `COleClientItem` hiçbir x veya y sahip nesneleri uzantı serileştirilir. Bu geçersiz kılma TRUE döndürerek yapılır `IsBlank` hiçbir x veya y öğesi olduğunda kapsam.  
  
 Serileştirme sırasında diğer işlemleri uygulamak istiyorsanız, bu işlev geçersiz kılar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDocument sınıfı](../../mfc/reference/coledocument-class.md)   
 [Coleserverıtem sınıfı](../../mfc/reference/coleserveritem-class.md)   
 [COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)
