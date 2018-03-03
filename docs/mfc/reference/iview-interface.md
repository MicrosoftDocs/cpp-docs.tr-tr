---
title: IView arabirimi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
dev_langs:
- C++
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4266d8f5ec564dac67d7167c6c9bab4768a0276
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="iview-interface"></a>IView arabirimi
Birkaç yöntemlerini uygular, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) için yönetilen bir denetimin görünüm bildirimleri göndermek için kullanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
interface class IView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IView::OnActivateView](#onactivateview)|Bir görünüm etkinleştirilmiş veya devre dışı olduğunda MFC tarafından çağrılır.|  
|[IView::OnInitialUpdate](#oninitialupdate)|Görünüm ilk belgeye eklendikten sonra ancak görünümü başlangıçta görüntülenmeden önce çerçevesi tarafından çağrılır.|  
|[IView::OnUpdate](#onupdate)|Görünümün belge değiştirildikten sonra MFC tarafından çağrılır; Bu işlev görünümünü değişiklikleri yansıtacak şekilde güncelleştirmek görünümü sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IView`birkaç yöntemlerini uygular, `CWinFormsView` yönetilen bir barındırılan denetime genel görünümü bildirimleri kullanır. Bunlar [OnInitialUpdate](#oninitialupdate), [in](#onupdate) ve [OnActivateView](#onactivateview).  
  
 `IView`benzer [CView](../../mfc/reference/cview-class.md), ancak yalnızca yönetilen görünümler ve denetimleri ile kullanılır.  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  

## <a name="requirements"></a>Gereksinimler  
 Başlık: afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll tanımlanan)  

## <a name="onactivateview"></a>IView::OnActivateView  
Bir görünüm etkinleştirilmiş veya devre dışı olduğunda MFC tarafından çağrılır.
```
void OnActivateView(bool activate);
```
## <a name="parameters"></a>Parametreler
`activate`  
Görünüm belirtir etkin veya devre dışı.  

## <a name="oninitialupdate"></a>IView::OnInitialUpdate
Görünüm ilk belgeye eklendikten sonra ancak görünümü başlangıçta görüntülenmeden önce çerçevesi tarafından çağrılır.
```
void OnInitialUpdate();
```

## <a name="onupdate"></a>IView::OnUpdate 
MFC tarafından görünümün belge değiştirildikten sonra çağrılır.  
```
void OnUpdate();
```
## <a name="remarks"></a>Açıklamalar  
Bu işlev görünümünü değişiklikleri yansıtacak şekilde güncelleştirmek görünümü sağlar.

## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinFormsView sınıfı](../../mfc/reference/cwinformsview-class.md)   
 [CView Sınıfı](../../mfc/reference/cview-class.md)
