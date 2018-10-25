---
title: DEVNAMES yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DEVNAMES
dev_langs:
- C++
helpviewer_keywords:
- DEVNAMES [MFC]
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d91a44a38d331a49927d5129c5002eef53c224ad
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077978"
---
# <a name="devnames-structure"></a>DEVNAMES Yapısı

`DEVNAMES` Yapı sürücü, cihaz ve çıkış bağlantı noktasına adları yazıcı için dizeleri içerir.

## <a name="syntax"></a>Sözdizimi

```
typedef struct tagDEVNAMES { /* dvnm */
    WORD wDriverOffset;
    WORD wDeviceOffset;
    WORD wOutputOffset;
    WORD wDefault; */* driver,
    device,
    and port-name strings follow wDefault */
} DEVNAMES;
```

#### <a name="parameters"></a>Parametreler

*wDriverOffset*<br/>
(Giriş/çıkış) Uzantısız () cihaz sürücüsünün içeren null ile sonlandırılmış bir dize karakterlerine uzaklığını belirtir. Giriş, bu dize, başlangıçta iletişim kutusunda görüntülemek için yazıcı belirlemek için kullanılır.

*wDeviceOffset*<br/>
(Giriş/çıkış) Cihazın adını içeren null ile sonlandırılmış dize (en fazla 32 bayt null dahil olmak üzere) karakterlerine uzaklığını belirtir. Bu dize aynı `dmDeviceName` üyesi [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) yapısı.

*wOutputOffset*<br/>
(Giriş/çıkış) Fiziksel çıkış Orta (çıkış bağlantı noktasına) bir DOS aygıtı adı içeren null ile sonlandırılmış dize karakterlerine uzaklığını belirtir.

*wDefault*<br/>
Dizeleri içerdiği olup olmadığını belirtir `DEVNAMES` varsayılan yazıcı yapısını tanımlar. Bu dize, varsayılan yazıcı son yazdırma işlemi bu yana değişmemiştir doğrulamak için kullanılır. DN_DEFAULTPRN bayrağı ayarlandıysa, giriş, diğer değerler `DEVNAMES` yapısı, geçerli varsayılan yazıcı karşı denetlenir. Dizelerden herhangi birinde eşleşmiyorsa kullanıcının belgeyi yeniden biçimlendirildi gerekebilir bildiren bir uyarı iletisi görüntülenir. Çıktıyı `wDefault` üye, yalnızca Yazıcı Ayarları iletişim kutusunda görüntülenen ve Tamam düğmesine kullanıcının seçtiği değiştirilir. Varsayılan yazıcı seçtiyseniz DN_DEFAULTPRN bayrağı ayarlanır. Belirli bir yazıcı seçtiyseniz bayrağı ayarlı değil. Bu üye içindeki diğer tüm bitleri Yazdır iletişim kutusu yordamı tarafından iç kullanım için ayrılmıştır.

## <a name="remarks"></a>Açıklamalar

`PrintDlg` İşlev üyeleri sistem tarafından tanımlanan Yazdır iletişim kutusunu başlatmak için bu dizeler kullanır. Kullanıcı iletişim kutusu kapanır, seçili bilgilerinden bu yapıda döndürülür.

## <a name="requirements"></a>Gereksinimler

**Başlık:** commdlg.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)

