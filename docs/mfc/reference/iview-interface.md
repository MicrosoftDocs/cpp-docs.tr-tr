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
ms.openlocfilehash: 7684ef034acd247355b3f572c86fcb80cb126b0c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594356"
---
# <a name="iview-interface"></a>IView arabirimi

Çeşitli yöntemler uygular, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) yönetilen bir denetim için görünüm bildirimlerini göndermek için kullanır.

## <a name="syntax"></a>Sözdizimi

```
interface class IView
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IView::OnActivateView](#onactivateview)|Bir görünümü etkinleştirmek veya MFC tarafından çağrılır.|
|[IView::OnInitialUpdate](#oninitialupdate)|Görünüm ilk belgeye eklendikten sonra ancak görünüm başlangıçta görüntülenmeden önce framework tarafından çağırılır.|
|[IView::OnUpdate](#onupdate)|Görünümün belge değiştirildikten sonra MFC tarafından çağrılır; Bu işlev görünümünü değişiklikleri yansıtacak şekilde güncelleştirilecek görünümü sağlar.|

## <a name="remarks"></a>Açıklamalar

`IView` çeşitli yöntemler uygular, `CWinFormsView` barındırılan ve yönetilen bir denetime genel görünümü bildirimleri iletecek şekilde kullanır. Bunlar [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) ve [OnActivateView](#onactivateview).

`IView` benzer [CView](../../mfc/reference/cview-class.md), ancak yalnızca yönetilen görünümleri ve denetimleri ile kullanılır.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="requirements"></a>Gereksinimler

Başlık: afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll içinde tanımlanmıştır)

## <a name="onactivateview"></a> IView::OnActivateView

Bir görünümü etkinleştirmek veya MFC tarafından çağrılır.
```
void OnActivateView(bool activate);
```

## <a name="parameters"></a>Parametreler

*Etkinleştirme*<br/>
Görünüm belirtir etkin veya devre dışı.

## <a name="oninitialupdate"></a> IView::OnInitialUpdate

Görünüm ilk belgeye eklendikten sonra ancak görünüm başlangıçta görüntülenmeden önce framework tarafından çağırılır.
```
void OnInitialUpdate();
```

## <a name="onupdate"></a> IView::OnUpdate

MFC tarafından görünümün belge değiştirildikten sonra çağırılır.
```
void OnUpdate();
```

## <a name="remarks"></a>Açıklamalar

Bu işlev görünümünü değişiklikleri yansıtacak şekilde güncelleştirilecek görünümü sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[CWinFormsView Sınıfı](../../mfc/reference/cwinformsview-class.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)
