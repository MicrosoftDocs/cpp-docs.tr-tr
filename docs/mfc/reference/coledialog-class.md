---
description: 'Daha fazla bilgi edinin: Cotadialog sınıfı'
title: Coeldialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
ms.openlocfilehash: 9bdb532d58136ac2aac622fa88f674e60ec7221e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227305"
---
# <a name="coledialog-class"></a>Coeldialog sınıfı

OLE için iletişim kutularında ortak işlevsellik sağlar.

## <a name="syntax"></a>Syntax

```
class COleDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Colet Iletişim kutusu:: GetLastError](#getlasterror)|İletişim kutusu tarafından döndürülen hata kodunu alır.|

## <a name="remarks"></a>Açıklamalar

Microsoft Foundation Class Kitaplığı, öğesinden türetilmiş çeşitli sınıflar sağlar `COleDialog` :

- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)

- [Cotaconvertdialog](../../mfc/reference/coleconvertdialog-class.md)

- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)

- [Cotalinksdialog](../../mfc/reference/colelinksdialog-class.md)

- [Cotabusi Iletişim kutusu](../../mfc/reference/colebusydialog-class.md)

- [Cotaupdatedialog](../../mfc/reference/coleupdatedialog-class.md)

- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)

- [Cotapropertiesiletişim kutusu](../../mfc/reference/colepropertiesdialog-class.md)

- [Colet Changesourcedialog](../../mfc/reference/colechangesourcedialog-class.md)

OLE 'e özgü iletişim kutuları hakkında daha fazla bilgi için [OLE 'deki makale Iletişim kutularına](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[Ccommoniletişim kutusu](../../mfc/reference/ccommondialog-class.md)

`COleDialog`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxodlgs. h

## <a name="coledialoggetlasterror"></a><a name="getlasterror"></a> Colet Iletişim kutusu:: GetLastError

`GetLastError`IDADTT döndürdüğünde ek hata bilgileri almak için üye işlevini çağırın `DoModal` .

```
UINT GetLastError() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından döndürülen hata kodları, `GetLastError` belirtilen iletişim kutusuna göre değişir.

### <a name="remarks"></a>Açıklamalar

`DoModal`Belirli hata iletileri hakkında bilgi için türetilmiş sınıflarda üye işlevine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
