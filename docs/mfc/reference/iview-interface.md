---
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
ms.openlocfilehash: 22e08a70ff4cc742406a1489899c0ba1df7eb664
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78872452"
---
# <a name="iview-interface"></a>IView arabirimi

, Yönetilen bir denetime görüntüleme bildirimleri göndermek için [CWinFormsView](../../mfc/reference/cwinformsview-class.md) tarafından kullanılan çeşitli yöntemler uygular.

## <a name="syntax"></a>Sözdizimi

```
interface class IView
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IView:: OnActivateView](#onactivateview)|Bir görünüm etkinleştirildiğinde veya devre dışı bırakıldığında MFC tarafından çağırılır.|
|[IView:: OnInitialUpdate](#oninitialupdate)|Görünüm belgeye ilk iliştirildikten sonra, ancak görünüm ilk görüntülenmeden önce Framework tarafından çağırılır.|
|[IView:: OnUpdate](#onupdate)|Görünümün belgesi değiştirildikten sonra MFC tarafından çağırılır; Bu işlev, görünümün değişiklikleri yansıtacak şekilde görünümünü güncelleştirmesine izin verir.|

## <a name="remarks"></a>Açıklamalar

`IView`, ortak görünüm bildirimlerini barındırılan yönetilen bir denetime iletmek için `CWinFormsView` tarafından kullanılan çeşitli yöntemler uygular. Bunlar [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) ve [OnActivateView](#onactivateview)' dir.

`IView`, [CView](../../mfc/reference/cview-class.md)ile benzerdir, ancak yalnızca yönetilen görünümler ve denetimlerle kullanılır.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="requirements"></a>Gereksinimler

Üst bilgi: afxwinforms. h (Assembly atlmfc\lib\mfcmifc80.dll derlemesinde tanımlanmıştır)

## <a name="onactivateview"></a>IView:: OnActivateView

Bir görünüm etkinleştirildiğinde veya devre dışı bırakıldığında MFC tarafından çağırılır.
```
void OnActivateView(bool activate);
```

## <a name="parameters"></a>Parametreler

*etkinleştirme*<br/>
Görünümün etkinleştirildiğini veya devre dışı bırakıldığını gösterir.

## <a name="oninitialupdate"></a>IView:: OnInitialUpdate

Görünüm belgeye ilk iliştirildikten sonra, ancak görünüm ilk görüntülenmeden önce Framework tarafından çağırılır.
```
void OnInitialUpdate();
```

## <a name="onupdate"></a>IView:: OnUpdate

Görünümün belgesi değiştirildikten sonra MFC tarafından çağırılır.
```
void OnUpdate();
```

## <a name="remarks"></a>Açıklamalar

Bu işlev, görünümün değişiklikleri yansıtacak şekilde görünümünü güncelleştirmesine izin verir.

## <a name="see-also"></a>Ayrıca bkz.

[CWinFormsView Sınıfı](../../mfc/reference/cwinformsview-class.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)
