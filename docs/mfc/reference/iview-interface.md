---
description: 'Daha fazla bilgi edinin: IView arabirimi'
title: IView arabirimi
ms.date: 11/04/2016
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
ms.openlocfilehash: e0229d61d12638935d7e4d928626a4bd7f5a830a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219453"
---
# <a name="iview-interface"></a>IView arabirimi

, Yönetilen bir denetime görüntüleme bildirimleri göndermek için [CWinFormsView](../../mfc/reference/cwinformsview-class.md) tarafından kullanılan çeşitli yöntemler uygular.

## <a name="syntax"></a>Syntax

```
interface class IView
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IView:: OnActivateView](#onactivateview)|Bir görünüm etkinleştirildiğinde veya devre dışı bırakıldığında MFC tarafından çağırılır.|
|[IView:: OnInitialUpdate](#oninitialupdate)|Görünüm belgeye ilk iliştirildikten sonra, ancak görünüm ilk görüntülenmeden önce Framework tarafından çağırılır.|
|[IView:: OnUpdate](#onupdate)|Görünümün belgesi değiştirildikten sonra MFC tarafından çağırılır; Bu işlev, görünümün değişiklikleri yansıtacak şekilde görünümünü güncelleştirmesine izin verir.|

### <a name="remarks"></a>Açıklamalar

`IView``CWinFormsView`ortak görünüm bildirimlerini barındırılan yönetilen bir denetime iletmek için kullanan çeşitli yöntemler uygular. Bunlar [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) ve [OnActivateView](#onactivateview)' dir.

`IView` , [CView](../../mfc/reference/cview-class.md)öğesine benzerdir, ancak yalnızca yönetilen görünümler ve denetimler ile kullanılır.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="requirements"></a>Gereksinimler

Üstbilgi: afxwinforms. h (derlemede tanımlanan atlmfc\lib\mfcmifc80.dll)

## <a name="iviewonactivateview"></a><a name="onactivateview"></a> IView:: OnActivateView

Bir görünüm etkinleştirildiğinde veya devre dışı bırakıldığında MFC tarafından çağırılır.

```cpp
void OnActivateView(bool activate);
```

## <a name="parameters"></a>Parametreler

*etkinleştir*<br/>
Görünümün etkinleştirildiğini veya devre dışı bırakıldığını gösterir.

## <a name="iviewoninitialupdate"></a><a name="oninitialupdate"></a> IView:: OnInitialUpdate

Görünüm belgeye ilk iliştirildikten sonra, ancak görünüm ilk görüntülenmeden önce Framework tarafından çağırılır.

```cpp
void OnInitialUpdate();
```

## <a name="iviewonupdate"></a><a name="onupdate"></a> IView:: OnUpdate

Görünümün belgesi değiştirildikten sonra MFC tarafından çağırılır.

```cpp
void OnUpdate();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, görünümün değişiklikleri yansıtacak şekilde görünümünü güncelleştirmesine izin verir.

## <a name="see-also"></a>Ayrıca bkz.

[CWinFormsView sınıfı](../../mfc/reference/cwinformsview-class.md)<br/>
[CView sınıfı](../../mfc/reference/cview-class.md)
