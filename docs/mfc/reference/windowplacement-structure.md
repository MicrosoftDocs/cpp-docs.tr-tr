---
title: "WINDOWPLACEMENT yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WINDOWPLACEMENT
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPLACEMENT structure [MFC]
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e73065cdf20d68b1da4ba77d1ad555e2bf95e937
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="windowplacement-structure"></a>WINDOWPLACEMENT Yapısı
`WINDOWPLACEMENT` Yapısı ekranında bir pencere yerleşimi hakkında bilgi içeren**.**  
  
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
 *uzunluğu*  
 Yapısı bayt cinsinden uzunluğu belirtir**.**  
  
 `flags`  
 Simge durumuna küçültülmüş pencereyi ve pencere geri yüklenen yöntemi konumunu denetlemek bayrakları belirtir. Bu üye birini veya her ikisini aşağıdaki bayraklar olabilir:  
  
- **WPF_SETMINPOSITION** x - ve y-konumlarını simge durumuna küçültülmüş pencereyi belirtilebilir belirtir**.** Bu bayrak olmalıdır koordinatları ayarlanmış olmadığını belirtilen **ptMinPosition** üyesi.  
  
- **WPF_RESTORETOMAXIMIZED** geri yüklenen pencere, simge önce olup olmadığını, ekranı bağımsız olarak ekranı olduğunu belirtir. Bu ayar yalnızca pencere geri sonraki zaman geçerlidir. Varsayılan geri yükleme davranışını değiştirmez. Yalnızca geçerli olduğunda bu bayrak olan **SW_SHOWMINIMIZED** değeri için belirtilen **showCmd** üyesi.  
  
 *showCmd*  
 Pencerenin geçerli durumunu göster belirtir. Bu üye aşağıdaki değerlerden biri olabilir:  
  
- **SW_HIDE** penceresini gizler ve başka bir pencere için etkinleştirme geçirir.  
  
- **SW_MINIMIZE** belirtilen pencere en aza indirir ve üst düzey pencere sistemin listesinde etkinleştirir.  
  
- **SW_RESTORE** Activates ve bir pencere görüntüler. Pencereyi simge durumuna küçültülmüş veya ekranı, Windows, özgün boyutunu ve konumunu geri yükler (aynı **SW_SHOWNORMAL**).  
  
- **SW_SHOW** bir pencere etkinleştirir ve onun geçerli boyutunu ve konumunu görüntüler.  
  
- **SW_SHOWMAXIMIZED** bir pencere etkinleştirir ve kaplamış görüntüler.  
  
- **SW_SHOWMINIMIZED** bir pencere etkinleştirir ve simge olarak görüntüler.  
  
- **SW_SHOWMINNOACTIVE** bir pencereyi simge olarak görüntüler. Şu anda etkin olan penceresi etkin kalır.  
  
- **SW_SHOWNA** geçerli durumunda bir pencere görüntüler. Şu anda etkin olan penceresi etkin kalır.  
  
- **SW_SHOWNOACTIVATE** bir pencere, en son boyutunu ve konumunu görüntüler. Şu anda etkin olan penceresi etkin kalır.  
  
- **SW_SHOWNORMAL** Activates ve bir pencere görüntüler. Pencereyi simge durumuna küçültülmüş veya ekranı, Windows, özgün boyutunu ve konumunu geri yükler (aynı **SW_RESTORE**).  
  
 *ptMinPosition*  
 Simge durumuna küçültülmüş pencerenin sol üst köşesinin konumunu belirtir.  
  
 `ptMaxPosition`  
 Pencere ekranı pencerenin sol üst köşesinin konumunu belirtir.  
  
 *rcNormalPosition*  
 Pencereyi normal (geri yüklenen) konumda olduğunda pencerenin koordinatları belirtir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)

