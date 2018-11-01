---
title: WINDOWPLACEMENT Yapısı
ms.date: 11/04/2016
f1_keywords:
- WINDOWPLACEMENT
helpviewer_keywords:
- WINDOWPLACEMENT structure [MFC]
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
ms.openlocfilehash: fecca306045805661a7799aca8d9ea57ea11f5b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518683"
---
# <a name="windowplacement-structure"></a>WINDOWPLACEMENT Yapısı

`WINDOWPLACEMENT` Yapı ekranında bir pencere yerleşimini hakkında bilgi içerir.

## <a name="syntax"></a>Sözdizimi

```
typedef struct tagWINDOWPLACEMENT {     /* wndpl */
    UINT length;
    UINT flags;
    UINT showCmd;
    POINT ptMinPosition;
    POINT ptMaxPosition;
    RECT rcNormalPosition;
} WINDOWPLACEMENT;
```

#### <a name="parameters"></a>Parametreler

*Uzunluğu*<br/>
Yapının bayt cinsinden uzunluğunu belirtir.

*bayrakları*<br/>
Simge durumuna küçültülmüş pencereyi ve pencereyi geri yüklendi yöntemi konumunu denetim bayrakları belirtir. Bu üye, birini veya ikisini de aşağıdaki bayraklar olabilir:

- X - ve y-konumlarını simge durumuna küçültülmüş pencereyi belirtilebilir WPF_SETMINPOSITION belirtir. Bu bayrak olmalıdır koordinatları ayarlanıp ayarlanmadığını belirtilen `ptMinPosition` üyesi.

- Geri yüklenen pencere, simge önce olup olmadığını, ekranı bağımsız olarak ekranı, WPF_RESTORETOMAXIMIZED belirtir. Bu ayar yalnızca pencereyi geri sonraki kez geçerli değil. Varsayılan geri yükleme davranışını değiştirmez. Bu bayrağı yalnızca sw_showmınımızed değeri için belirtildiğinde geçerlidir `showCmd` üyesi.

*showCmd*<br/>
Pencerenin geçerli durumunu göster belirtir. Bu üye, aşağıdaki değerlerden biri olabilir:

- SW_HIDE penceresini gizler ve başka bir pencereye etkinleştirme geçirir.

- SW_MINIMIZE belirtilen pencereye en aza indirir ve sistemin listesinde en üst düzey penceresini etkinleştirir.

- SW_RESTORE etkinleştirir ve bir pencere görüntüler. Pencereyi simge durumuna küçültülmüş ya da tam ekran, Windows, onun özgün boyutunu ve konumunu (SW_SHOWNORMAL ile aynı) geri yükler.

- SW_SHOW bir pencereyi etkinleştirir ve geçerli boyutunu ve konumunu içinde görüntüler.

- Da sw_showmaxımızed bir pencereyi etkinleştirir ve kaplamış görüntüler.

- Sw_showmınımızed bir pencereyi etkinleştirir ve simge olarak görüntüler.

- SW_SHOWMINNOACTIVE simge olarak bir pencere görüntüler. Şu anda etkin olan pencerenin etkin kalır.

- SW_SHOWNA geçerli durumunda bir pencere görüntüler. Şu anda etkin olan pencerenin etkin kalır.

- SW_SHOWNOACTIVATE, en son boyut ve konum bir pencere görüntüler. Şu anda etkin olan pencerenin etkin kalır.

- SW_SHOWNORMAL etkinleştirir ve bir pencere görüntüler. Pencereyi simge durumuna küçültülmüş ya da tam ekran, Windows, onun özgün boyutunu ve konumunu (SW_RESTORE ile aynı) geri yükler.

*ptMinPosition*<br/>
Simge durumuna küçültülmüş pencerenin sol üst köşesinin konumunu belirtir.

*ptMaxPosition*<br/>
Penceresi büyütüldüğünde pencerenin sol üst köşesinin konumunu belirtir.

*rcNormalPosition*<br/>
Pencereyi normal (geri) konumda olduğunda pencerenin koordinatları belirtir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** winuser.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)

