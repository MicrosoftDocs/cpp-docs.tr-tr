---
title: Değişken parametre türü sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- VTS_YPOS_HIMETRIC
- VTS_PICTURE
- VTS_FONT
- VTS_XPOS_HIMETRIC
- VTS_XPOS_PIXELS
- VTS_XSIZE_HIMETRIC
- VTS_YPOS_PIXELS
- VTS_TRISTATE
- VTS_HANDLE
- VTS_YSIZE_HIMETRIC
- VTS_COLOR
- VTS_OPTEXCLUSIVE
- VTS_YSIZE_PIXELS
- VTS_XSIZE_PIXELS
dev_langs:
- C++
helpviewer_keywords:
- VTS_XPOS_HIMETRIC constant [MFC]
- VTS_FONT constant [MFC]
- VTS_XPOS_PIXELS constant [MFC]
- VTS_COLOR constant [MFC]
- Variants [MFC]
- VTS_YPOS_PIXELS constant [MFC]
- VTS_YSIZE_HIMETRIC constant [MFC]
- VTS_YPOS_HIMETRIC constant [MFC]
- Variants, parameter type constants
- Variant data constants [MFC]
- VTS_PICTURE constant [MFC]
- VTS_TRISTATE constant [MFC]
- VTS_XSIZE_HIMETRIC constant [MFC]
- VTS_HANDLE constant [MFC]
- VTS_XSIZE_PIXELS constant [MFC]
- VTS_OPTEXCLUSIVE constant [MFC]
- VTS_YSIZE_PIXELS constant [MFC]
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 64b68fb930c6de732e009a251c5e8363bace80ec
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374743"
---
# <a name="variant-parameter-type-constants"></a>Değişken Parametre Türü Sabitleri

Bu konu, Microsoft Foundation Class Kitaplığı OLE denetim sınıfları ile kullanılmak üzere tasarlanmış değişken parametre türü gösteren yeni sabitleri listeler.

Sınıf sabit listesi verilmiştir:

##  <a name="_mfc_variant_data_constants"></a> Değişken veri sabitleri

- VTS_COLOR bir 32 bit tamsayı RGB renk değerleri temsil etmek için kullanılır.

- VTS_FONT bir işaretçi `IFontDisp` OLE yazı tipi nesnesinin arabirimi.

- VTS_HANDLE A Windows tanıtıcı değeri.

- Vts_pıcture bir işaretçi `IPictureDisp` arabirimi OLE Resim nesnesi.

- Bir grup radyo düğmeleri gibi denetimleri kullanılmak üzere tasarlanan bir denetim için kullanılan vts_optexclusıve bir 16 bitlik değer. Bu tür bir denetim grubundaki TRUE değeri varsa, diğerlerini FALSE olmalıdır kapsayıcı söyler.

- Vts_trıstate bir 16 bitlik işaretli tamsayı üç olası değer (Seçilen temizlenmiş, kullanılamaz), örneğin, bir onay kutusu birine sahip özellikler için kullanılır.

- HIMETRIC birimleri x ekseni boyunca bir konumu temsil etmek için kullanılan vts_xpos_hımetrıc bir 32-bit işaretsiz tamsayı.

- Y ekseni boyunca HIMETRIC birimleri bir konumu temsil etmek için kullanılan vts_ypos_hımetrıc bir 32-bit işaretsiz tamsayı.

- Piksel olarak x ekseni boyunca bir konumu temsil etmek için kullanılan vts_xpos_pıxels bir 32-bit işaretsiz tamsayı.

- Piksel olarak y ekseni boyunca bir konumu temsil etmek için kullanılan vts_ypos_pıxels bir 32-bit işaretsiz tamsayı.

- Bir ekran nesnesinin piksel cinsinden genişliği temsil etmek için kullanılan vts_xsıze_pıxels bir 32-bit işaretsiz tamsayı.

- Bir ekran nesnesinin piksel cinsinden yüksekliğini temsil etmek için kullanılan vts_ysıze_pıxels bir 32-bit işaretsiz tamsayı.

- Bir ekran nesnesi HIMETRIC biriminde genişliğini temsil etmek için kullanılan vts_xsıze_hımetrıc bir 32-bit işaretsiz tamsayı.

- Bir ekran nesnesi HIMETRIC biriminde yüksekliğini temsil etmek için kullanılan vts_ysıze_hımetrıc bir 32-bit işaretsiz tamsayı.

    > [!NOTE]
    >  Değişken veri sabit bir işaretçi sağlayan tüm değişken türleri için VTS_FONT ve vts_pıcture, hariç olmak üzere ek değişken sabitleri tanımlanmadı. VTS_P kullanarak bu sabitleri adlı`constantname` kuralı. Örneğin, VTS_PCOLOR VTS_COLOR sabiti bir işaretçisidir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
