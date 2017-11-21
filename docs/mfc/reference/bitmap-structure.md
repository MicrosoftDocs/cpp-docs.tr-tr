---
title: "Bit eşlem yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BITMAP
dev_langs: C++
helpviewer_keywords: BITMAP structure [MFC]
ms.assetid: 05d33b4d-7232-4643-a108-87dda8ff5f22
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 155fb93a22170f3458d9b376ea64c2ed89536cda
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bitmap-structure"></a>BITMAP Yapısı
**Bit eşlem** yapısını tanımlar yüksekliğini, genişlik, renk biçimi ve mantıksal bir bit eşlem bit değerleri**.**  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagBITMAP {  /* bm */  
    int bmType;  
    int bmWidth;  
    int bmHeight;  
    int bmWidthBytes;  
    BYTE bmPlanes;  
    BYTE bmBitsPixel;  
    LPVOID bmBits;  
} BITMAP;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *bmType*  
 Bit eşlem türünü belirtir. Mantıksal bit eşlemler için bu üye 0 olmalıdır.  
  
 *bmWidth*  
 Bit eşlem genişliğini piksel cinsinden belirtir. Genişlik 0'dan büyük olmalıdır.  
  
 *bmHeight*  
 Izgara satırlarında bit eşlem yüksekliğini belirtir. Yüksekliği 0'dan büyük olmalıdır.  
  
 *bmWidthBytes*  
 Her ızgara satır bayt sayısını belirtir. Grafik cihaz arabirimi (GDI) bir bit eşlem bit değerleri tamsayı (2-bayt) değerleri dizisi form varsayar olduğundan bu değer bir çift sayı olmalıdır. Diğer bir deyişle, **bmWidthBytes** \* 8 16 ne zaman elde değerine eşit veya daha büyük bir sonraki katları olmalıdır **bmWidth** üye çarpılarak **bmBitsPixel**  üyesi.  
  
 *bmPlanes*  
 Renk düzlemi sayısı eşleminde belirtir.  
  
 *bmBitsPixel*  
 Bir piksel tanımlamak için gerekli her düzlemi bitişik renk bit sayısını belirtir.  
  
 *bmBits*  
 Bit eşlem bit değerleri konumunu işaret. **BmBits** üye 1 bayt değerleri dizisi için uzun bir işaretçi olması gerekir.  
  
## <a name="remarks"></a>Açıklamalar  
 Şu anda kullanılan bit eşlem biçimler şunlardır: tek renkli ve rengi. Tek renkli bitmap 1-bit, 1-düzlemi biçimi kullanır. Her tarama 16 bit katı.  
  
 Taramaları şu şekilde bir tek renkli yükseklik bit eşlem için düzenlenmiş  *n* :  
  
 `Scan 0`  
  
 `Scan 1`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 `Scan n-2`  
  
 `Scan n-1`  
  
 Her iki siyah pikseldir tek renkli bir cihazda veya beyaz. Bit eşlem karşılık gelen bit 1 ise, piksel (beyaz) üzerinde çevrilir. Bit eşlem karşılık gelen bit 0 ise, piksel (siyah) çevrilir.  
  
 Tüm cihazlar sahip bit eşlemler Destek **RC_BITBLT** bit kümesinde **RASTERCAPS** dizini [CDC::GetDeviceCaps](../../mfc/reference/cdc-class.md#getdevicecaps) üye işlevi.  
  
 Her aygıt, kendi benzersiz renk biçime sahip. Bir bit eşlem bir aygıttan başka bir bilgisayara aktarmak için kullanılması [GetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd144879) ve [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) Windows çalışır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)
