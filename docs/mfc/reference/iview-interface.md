---
title: IView Arayüzü
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
ms.openlocfilehash: dfe77699a51ad2670c703d02e13e9062e76debcd
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751289"
---
# <a name="iview-interface"></a>IView Arayüzü

[CWinFormsView'in](../../mfc/reference/cwinformsview-class.md) görüntü bildirimlerini yönetilen bir denetime göndermek için kullandığı çeşitli yöntemler uygular.

## <a name="syntax"></a>Sözdizimi

```
interface class IView
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IView::OnActivateView](#onactivateview)|Bir görünüm etkinleştirildiğinde veya devre dışı bırakıldığında MFC tarafından çağrılır.|
|[IView::OnInitialUpdate](#oninitialupdate)|Görünüm belgeye ilk iliştirildikten sonra çerçeve tarafından çağrılır, ancak görünüm ilk görüntülenmeden önce.|
|[IView::Onupdate](#onupdate)|Görünümün belgesi değiştirildikten sonra MFC tarafından çağrılan; bu işlev, görünümün değişiklikleri yansıtacak şekilde ekranını güncelleştirmesini sağlar.|

## <a name="remarks"></a>Açıklamalar

`IView`ortak görünüm bildirimlerini barındırılan yönetilen denetime iletmek için `CWinFormsView` kullanılan çeşitli yöntemler uygular. Bunlar [OnInitialUpdate,](#oninitialupdate) [OnUpdate](#onupdate) ve [OnActivateView](#onactivateview)vardır.

`IView`[CView'a](../../mfc/reference/cview-class.md)benzer, ancak yalnızca yönetilen görünümler ve denetimlerle kullanılır.

Windows Formlarını kullanma hakkında daha fazla bilgi [için](../../dotnet/using-a-windows-form-user-control-in-mfc.md)bkz.

## <a name="requirements"></a>Gereksinimler

Başlık: afxwinforms.h (montaj atlmfc\lib\mfcmifc80.dll tanımlanır)

## <a name="iviewonactivateview"></a><a name="onactivateview"></a>IView::OnActivateView

Bir görünüm etkinleştirildiğinde veya devre dışı bırakıldığında MFC tarafından çağrılır.

```cpp
void OnActivateView(bool activate);
```

## <a name="parameters"></a>Parametreler

*Etkinleştirmek*<br/>
Görünümün etkinleştirilip etkinleştirilmediğini veya devre dışı bırakıldığını gösterir.

## <a name="iviewoninitialupdate"></a><a name="oninitialupdate"></a>IView::OnInitialUpdate

Görünüm belgeye ilk iliştirildikten sonra çerçeve tarafından çağrılır, ancak görünüm ilk görüntülenmeden önce.

```cpp
void OnInitialUpdate();
```

## <a name="iviewonupdate"></a><a name="onupdate"></a>IView::Onupdate

Görünümün belgesi değiştirildikten sonra MFC tarafından çağrılır.

```cpp
void OnUpdate();
```

## <a name="remarks"></a>Açıklamalar

Bu işlev, görünümün değişiklikleri yansıtacak şekilde ekranını güncelleştirmesini sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[CWinFormsView Sınıfı](../../mfc/reference/cwinformsview-class.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)
