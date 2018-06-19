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
ms.openlocfilehash: 13820ff4fb07c3743f36ba3ebe33ee56a3a79c7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379866"
---
# <a name="variant-parameter-type-constants"></a>Değişken Parametre Türü Sabitleri
Bu konu Microsoft Foundation Class Kitaplığı OLE denetim sınıfları ile kullanılmak üzere tasarlanmış değişken parametre türü belirtmek yeni sabitleri listeler.  
  
 Sınıf sabitleri listesi aşağıdadır:  
  
##  <a name="_mfc_variant_data_constants"></a> Değişken veri sabitleri  
  
-   **VTS_COLOR** bir RGB renk değeri temsil etmek için kullanılan bir 32 bit tamsayı.  
  
-   **VTS_FONT** gösteren bir işaretçi **IFontDisp** OLE yazı tipi nesnesinin arabirimi.  
  
-   **VTS_HANDLE** bir Windows tanıtıcı değeri.  
  
-   **Vts_pıcture** gösteren bir işaretçi `IPictureDisp` OLE resim nesnesinin arabirimi.  
  
-   **Vts_optexclusıve** radyo düğmeleri gibi denetimleri grubundaki kullanılması hedeflenen bir denetim için kullanılan bir 16 bit değeri. Bu tür kapsayıcı bir denetim, bir grup olduğunu bildiren bir **TRUE** değeri, diğerlerini olmalıdır **FALSE**.  
  
-   **Vts_trıstate** bir 16 bit işaretli tamsayıyı kullanılan üç olası değerlerden (Seçilen temizlenmiş, kullanılamaz), örneğin, sahip özellikler için bir onay kutusu.  
  
-   **Vts_xpos_hımetrıc** içinde x ekseni boyunca bir konumu temsil etmek için kullanılan bir 32 bit işaretsiz tamsayıyı **HIMETRIC** birimleri.  
  
-   **Vts_ypos_hımetrıc** içinde y ekseni boyunca bir konumu temsil etmek için kullanılan bir 32 bit işaretsiz tamsayıyı **HIMETRIC** birimleri.  
  
-   **Vts_xpos_pıxels** bir 32 bit işaretsiz tamsayıyı x ekseni boyunca konumunu piksel cinsinden göstermek için kullanılır.  
  
-   **Vts_ypos_pıxels** piksel cinsinden y ekseni boyunca bir konumu temsil etmek için kullanılan bir 32 bit işaretsiz tamsayıyı.  
  
-   **Vts_xsıze_pıxels** bir 32 bit işaretsiz tamsayıyı ekran nesne piksel cinsinden genişliği göstermek için kullanılır.  
  
-   **Vts_ysıze_pıxels** bir 32 bit işaretsiz tamsayıyı ekran nesne piksel cinsinden yüksekliği göstermek için kullanılır.  
  
-   **Vts_xsıze_hımetrıc** bir ekran nesnesinde genişliğini temsil etmek için kullanılan bir 32 bit işaretsiz tamsayıyı **HIMETRIC** birimleri.  
  
-   **Vts_ysıze_hımetrıc** bir ekran nesnesinde yüksekliğini temsil etmek için kullanılan bir 32 bit işaretsiz tamsayıyı **HIMETRIC** birimleri.  
  
    > [!NOTE]
    >  Ek değişken sabitleri dışında tüm değişken türleri için tanımlanmışsa **VTS_FONT** ve **vts_pıcture**, değişken veri ortak bir işaretçi sağlayın nstant. Kullanarak bu sabitleri adlı **VTS_P** `constantname` kuralı. Örneğin, **VTS_PCOLOR** gösteren bir işaretçidir bir **VTS_COLOR** sabit.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
