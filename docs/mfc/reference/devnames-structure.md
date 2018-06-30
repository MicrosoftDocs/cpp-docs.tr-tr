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
ms.openlocfilehash: 0c13167c42c6acbfcc5f3af500205eed6ab884d9
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121581"
---
# <a name="devnames-structure"></a>DEVNAMES Yapısı
`DEVNAMES` Yapısı sürücü, cihaz ve bir yazıcı için çıktı bağlantı noktası adları tanımlayan dizelerin içerir.  
  
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
 *wDriverOffset*  
 (Girdi/çıktı) Aygıt sürücüsünün adını (uzantısı olmadan) içeren null ile sonlandırılmış bir dizeye karakter uzaklığını belirtir. Giriş, bu dize, başlangıçta iletişim kutusunda görüntülemek için yazıcı belirlemek için kullanılır.  
  
 *wDeviceOffset*  
 (Girdi/çıktı) Cihaz adını içeren null ile sonlandırılmış dizesi (en fazla 32 null dahil olmak üzere bayt) için karakter cinsinden uzaklığını belirtir. Bu dize için özdeş olması gereken `dmDeviceName` üyesi [aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) yapısı.  
  
 *wOutputOffset*  
 (Girdi/çıktı) Fiziksel çıkış Orta (çıktı bağlantı noktası) için DOS aygıtı adı içeren null ile sonlandırılmış dizeye karakter uzaklığını belirtir.  
  
 *wDefault*  
 Dizeleri içinde yer alan olup olmadığını belirtir `DEVNAMES` varsayılan yazıcı yapısını tanımlar. Bu dize, varsayılan yazıcı son yazdırma işlemi bu yana değişmemiştir doğrulamak için kullanılır. DN_DEFAULTPRN bayrağı ayarlarsanız, giriş, diğer değerler `DEVNAMES` yapısı, geçerli varsayılan yazıcı karşı denetlenir. Dizelerden herhangi birinde eşleşmiyorsa, belgeyi yeniden biçimlendirilebileceği gerekebilir kullanıcı bildiren bir uyarı iletisi görüntülenir. Çıktıyı `wDefault` üye yalnızca Sayfa Yapısı iletişim kutusu görüntülenir ve kullanıcı Tamam düğmesine seçerseniz değiştirilir. Varsayılan yazıcı seçtiyseniz DN_DEFAULTPRN bayrağı ayarlanır. Belirli bir yazıcı seçtiyseniz bayrağı ayarlanmamış. Bu üye diğer tüm bitleri Yazdır iletişim kutusu yordamı tarafından iç kullanım için ayrılmıştır.  
  
## <a name="remarks"></a>Açıklamalar  
 `PrintDlg` İşlevi üyeleri sistem tarafından tanımlanan Yazdır iletişim kutusunda başlatmak için bu dizeler kullanır. Kullanıcı iletişim kutusu kapandığında seçili yazıcı ile ilgili bilgiler bu yapısında döndürülür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** commdlg.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)


