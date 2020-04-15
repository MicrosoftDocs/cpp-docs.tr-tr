---
title: COleDialog Sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
ms.openlocfilehash: 6a1983d426e97dd8063aee2857dc36557aa20677
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366088"
---
# <a name="coledialog-class"></a>COleDialog Sınıfı

OLE için iletişim kutularına ortak işlevsellik sağlar.

## <a name="syntax"></a>Sözdizimi

```
class COleDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleDialog::GetLastError](#getlasterror)|Hata kodunu iletişim kutusu tarafından döndürülür.|

## <a name="remarks"></a>Açıklamalar

Microsoft Hazırlık Sınıf Kitaplığı aşağıdakilerden `COleDialog`türetilen çeşitli sınıflar sağlar:

- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)

- [Coleconvertdialog](../../mfc/reference/coleconvertdialog-class.md)

- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)

- [Colelinksdialog](../../mfc/reference/colelinksdialog-class.md)

- [Colebusydialog](../../mfc/reference/colebusydialog-class.md)

- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)

- [Colepastespecialdialog](../../mfc/reference/colepastespecialdialog-class.md)

- [Colepropertiesdialog](../../mfc/reference/colepropertiesdialog-class.md)

- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)

OLE'ye özgü iletişim kutuları hakkında daha fazla bilgi için, [OLE'deki İletişim Kutuları makalesine](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`COleDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxodlgs.h

## <a name="coledialoggetlasterror"></a><a name="getlasterror"></a>COleDialog::GetLastError

IDABORT döndürdüğünde `GetLastError` `DoModal` ek hata bilgileri almak için üye işlevini arayın.

```
UINT GetLastError() const;
```

### <a name="return-value"></a>Dönüş Değeri

Döndürülen `GetLastError` hata kodları görüntülenen belirli iletişim kutusuna bağlıdır.

### <a name="remarks"></a>Açıklamalar

Belirli `DoModal` hata iletileri hakkında bilgi için türetilmiş sınıflardaki üye işlevine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
