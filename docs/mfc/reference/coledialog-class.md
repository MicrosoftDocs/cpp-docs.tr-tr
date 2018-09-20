---
title: COleDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
dev_langs:
- C++
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c6cebf6af24de860c583398c16c87824ede0075
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401283"
---
# <a name="coledialog-class"></a>COleDialog sınıfı

OLE iletişim kutularındaki ortak işlevselliği sağlar.

## <a name="syntax"></a>Sözdizimi

```
class COleDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDialog::GetLastError](#getlasterror)|İletişim kutusu tarafından döndürülen hata kodu alır.|

## <a name="remarks"></a>Açıklamalar

Microsoft Foundation Class Kitaplığı ile türetilmiş birkaç sınıflarını sağlar `COleDialog`:

- [Coleınsertdialog](../../mfc/reference/coleinsertdialog-class.md)

- [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)

- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)

- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)

- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)

- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)

- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)

- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)

Özel OLE iletişim kutuları hakkında daha fazla bilgi için bkz [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`COleDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxodlgs.h

##  <a name="getlasterror"></a>  COleDialog::GetLastError

Çağrı `GetLastError` ek hata bilgileri almak için üye işlevi, `DoModal` IDABORT döndürür.

```
UINT GetLastError() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından döndürülen hata kodlarını `GetLastError` belirli iletişim kutusunda görüntülenen bağlıdır.

### <a name="remarks"></a>Açıklamalar

Bkz: `DoModal` belirli hata iletileri hakkında bilgi için türetilmiş sınıflarda üye işlevi.

## <a name="see-also"></a>Ayrıca Bkz.

[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



