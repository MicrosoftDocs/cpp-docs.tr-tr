---
title: BITMAPINFO yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- BITMAPINFO
dev_langs:
- C++
helpviewer_keywords:
- BITMAPINFO structure [MFC]
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9b1bd896157d7f11792a5a6514e30ecd3d46a19
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336263"
---
# <a name="bitmapinfo-structure"></a>BITMAPINFO Yapısı
`BITMAPINFO` Boyutları ve bir Windows CİHAZDAN bağımsız bit eşlem (DIB) için renk bilgisi yapısını tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagBITMAPINFO {  
    BITMAPINFOHEADER bmiHeader;  
    RGBQUAD bmiColors[1];  
} BITMAPINFO;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *bmiHeader*  
 Belirtir bir [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) boyutları ve CİHAZDAN bağımsız bit eşlem renk biçimi hakkında bilgi içeren yapısı.  
  
 *bmiColors*  
 Bir dizi belirtir [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) ya da bit eşlem içinde Renk Tanımla DWORD veri türleri.  
  
## <a name="remarks"></a>Açıklamalar  
 CİHAZDAN bağımsız bit eşlem iki farklı bölümden oluşur: bir `BITMAPINFO` renkleri bit eşlemin ve bit eşlemin piksel belirten bir bayt dizisi ve boyutları açıklar yapısı. Dizideki BITS birlikte paketlenmiş, ancak her bir tarama satır bitiş sıfırlarla sıfır olmalıdır bir **uzun** sınır. Yüksekliği pozitif ise, bit eşlem kaynağı sol alt köşesinde ' dir. Yüksekliği negatif ise, kaynak üst sol löşede ' dir.  
  
 A *paketlenmiş bir bit eşlem* yeri bayt dizisinin hemen izleyen bir bit eşlem ise `BITMAPINFO` yapısı. Paketlenmiş bit eşlemler, tek bir işaretçi tarafından başvurulur.  
  
 Hakkında daha fazla bilgi için `BITMAPINFO` yapısı ve üyeleri için uygun değerleri `BITMAPINFOHEADER` ve `RGBQUAD` yapıları, Windows SDK belgelerinde aşağıdaki konulara bakın.  
  
- [BITMAPINFO yapısı](http://msdn.microsoft.com/library/windows/desktop/dd183375)  
  
- [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) yapısı  
  
- [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) yapısı  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBrush::CreateDIBPatternBrush](../../mfc/reference/cbrush-class.md#createdibpatternbrush)   
 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)   
 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)

