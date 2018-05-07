---
title: MFC sınıf nesnelerine atama yazın | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 217be53a78a65a0f617438127b922b20c950853d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="type-casting-of-mfc-class-objects"></a>MFC Sınıf Nesnelerine İlişkin Tür Atama
Tür atama makroları ile veya cast yasal denetlemeden belirli sınıftan bir nesneyi gösteren bir işaretçi için belirli bir işaretçi dönüştürmek için bir yol sağlar.  
  
 Aşağıdaki tabloda MFC tür atama makroları listeler.  
  
### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>MFC sınıf nesnelerine işaretçiler atama makroları  
  
|||  
|-|-|  
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|Cast yasal olup olmadığını görmek için kontrol edilirken bir sınıf nesnesi için bir işaretçi bir işaretçi çevirir.|  
|[STATIC_DOWNCAST](#static_downcast)|Bir işaretçi bir nesneye bir sınıftan ilgili türü işaretçisi çevirir. Bir hata ayıklama derlemesi neden olan bir **ASSERT** nesne değilse, bir "tür" hedef türü.|  
  
##  <a name="dynamic_downcast"></a>  DYNAMIC_DOWNCAST  
 Cast yasal olup olmadığını görmek için kontrol edilirken bir sınıf nesnesi için bir işaretçi bir işaretçi dönüştürmek için kullanışlı bir yöntem sağlar.  
  
```   
DYNAMIC_DOWNCAST(class, pointer)  
```  
  
### <a name="parameters"></a>Parametreler  
 `class`  
 Bir sınıf adı.  
  
 `pointer`  
 Bir nesne türü için bir işaretçi için dönüştürmek için bir işaretçi `class`.  
  
### <a name="remarks"></a>Açıklamalar  
 Makro cast `pointer` bir nesne için bir işaretçi parametresi `class` parametrenin türü.  
  
 İşaretçi tarafından başvurulan nesne ise bir "tür" tanımlanan sınıfı makrosu uygun işaretçi döndürür. Makro döndürür, yasal bir cast değilse, **NULL**.  
  
##  <a name="static_downcast"></a>  STATIC_DOWNCAST  
 Atamalar *pobject* için bir işaretçi bir *class_name* nesnesi.  
  
```   
STATIC_DOWNCAST(class_name, pobject)   
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Cast için sınıfı adı.  
  
 *pobject*  
 Bir işaretçi için dönüştürmek için işaretçiyi bir *class_name* nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 *pobject* ya da olmalıdır **NULL**, veya bir nesne doğrudan türetilmiş bir sınıf ya da dolaylı, gelen noktasına *class_name*. İle uygulamanızın derlemelerde **_DEBUG** tanımlanan önişlemci sembolü makrosu olacak **ASSERT** varsa *pobject* değil **NULL**, veya olmayan bir nesneye işaret ediyorsa bir "tür" Belirtilen sınıf *class_name* parametre (bkz [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)). İçinde olmayan **_DEBUG** derlemeleri, makrosu herhangi bir tür denetlemesi olmadan cast gerçekleştirir.  
  
 Belirtilen sınıf *class_name* parametresi türetilmeli `CObject` kullanmalıdır `DECLARE_DYNAMIC` ve `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` ve `IMPLEMENT_DYNCREATE`, veya `DECLARE_SERIAL` ve `IMPLEMENT_SERIAL`makalesinde açıklandığı gibi makroları [CObject sınıfı: CObject'ten sınıf türetme](../../mfc/deriving-a-class-from-cobject.md).  
  
 Örneğin, bir işaretçi cast `CMyDoc`adlı `pMyDoc`, bir işaretçi için **CDocument** Bu ifade kullanarak:  
  
 [!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]  
  
 Varsa `pMyDoc` doğrudan veya dolaylı olarak türetilen bir nesneye işaret etmiyor **CDocument**, makrosu olacak **ASSERT**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
