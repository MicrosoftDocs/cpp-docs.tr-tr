---
title: "BITMAPINFO yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BITMAPINFO
dev_langs:
- C++
helpviewer_keywords:
- BITMAPINFO structure [MFC]
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9d704fec4a6ae0a95bd393b4a7fffa24884711e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bitmapinfo-structure"></a>BITMAPINFO Yapısı
`BITMAPINFO` Yapısı boyutları ve bir Windows aygıt bağımsız bit eşlem (DIB) için renk bilgilerini tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagBITMAPINFO {  
    BITMAPINFOHEADER bmiHeader;  
    RGBQUAD bmiColors[1];  
} BITMAPINFO;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `bmiHeader`  
 Belirten bir [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) boyutları ve bir CİHAZDAN bağımsız bit eşlem renk biçimi hakkında bilgi içeren yapısı.  
  
 `bmiColors`  
 Bir dizi belirtir [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) veya `DWORD` eşleminde renkleri tanımlamak veri türleri.  
  
## <a name="remarks"></a>Açıklamalar  
 CİHAZDAN bağımsız bit eşlem iki farklı bölümden oluşur: bir `BITMAPINFO` boyutları ve bit eşlem renklerini ve eşleminde piksel belirten bir bayt dizisi açıklar yapısı. Dizi bitleri birlikte paketlenmiş, ancak her tarama satırının bitiş sıfırlarla doldurulan gerekir bir `LONG` sınır. Yüksekliği pozitif, bit eşlem kökeni sol alt köşesinde ise. Yüksekliği negatif başlangıcı sol üst köşesindeki ise.  
  
 A *paketlenmiş bit eşlem* burada bayt dizisi hemen izleyen bir bit eşlem ise `BITMAPINFO` yapısı. Paketlenmiş bit eşlemler, tek bir işaretçi tarafından başvurulur.  
  
 Hakkında daha fazla bilgi için `BITMAPINFO` yapısı ve üyeleri için değerlerin uygun `BITMAPINFOHEADER` ve `RGBQUAD` yapıları, Windows SDK belgelerinde aşağıdaki konulara bakın.  
  
- [BITMAPINFO yapısı](http://msdn.microsoft.com/library/windows/desktop/dd183375)  
  
- [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) yapısı  
  
- [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) yapısı  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBrush::CreateDIBPatternBrush](../../mfc/reference/cbrush-class.md#createdibpatternbrush)   
 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)   
 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)

