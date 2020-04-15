---
title: Değişken Parametre Türü Sabitleri
ms.date: 11/04/2016
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
ms.openlocfilehash: f73c72830216679f8a91d0037d48c1e1b8e400c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372860"
---
# <a name="variant-parameter-type-constants"></a>Değişken Parametre Türü Sabitleri

Bu konu, Microsoft Hazırlık Sınıfı Kitaplığı'nın OLE denetim sınıflarıyla kullanılmak üzere tasarlanmış varyant parametre türlerini gösteren yeni sabitleri listeler.

Aşağıda sınıf sabitlerinin bir listesi vetir:

## <a name="variant-data-constants"></a><a name="_mfc_variant_data_constants"></a>Varyant Veri Sabitleri

- VTS_COLOR RGB renk değerini temsil etmek için kullanılan 32 bit'lik bir tamsayı.

- VTS_FONT Bir OLE yazı tipi nesnesinin `IFontDisp` arabirimine işaretçi.

- VTS_HANDLE Windows işleişi değeri.

- VTS_PICTURE Bir OLE resim nesnesinin `IPictureDisp` arabirimine işaretçi.

- VTS_OPTEXCLUSIVE Radyo düğmeleri gibi bir denetim grubunda kullanılması amaçlanan bir denetim için kullanılan 16 bitlik bir değerdir. Bu tür kapsayıcı, bir gruptaki bir denetimin DOĞRU değeri varsa, diğerlerinin tümININ YANLIŞ olması gerektiğini söyler.

- VTS_TRISTATE Örneğin, üç olası değerden birine (seçili, temizlenmiş, kullanılamayan) sahip olabilecek özellikler için kullanılan 16 bit imzalı bir tamsayı.

- VTS_XPOS_HIMETRIC HIMETRIC birimlerinde x ekseni boyunca bir konumu temsil etmek için kullanılan 32 bit imzasız tamsayı.

- VTS_YPOS_HIMETRIC HIMETRIC birimlerinde y ekseni boyunca bir konumu temsil etmek için kullanılan 32 bit imzasız tamsayı.

- VTS_XPOS_PIXELS Piksellerde x ekseni boyunca bir konumu temsil etmek için kullanılan 32 bit imzasız tamsayı.

- VTS_YPOS_PIXELS Piksellerde y ekseni boyunca bir konumu temsil etmek için kullanılan 32 bit imzasız tamsayı.

- VTS_XSIZE_PIXELS Piksellerde bir ekran nesnesinin genişliğini temsil etmek için kullanılan 32 bit imzasız tamsayı.

- VTS_YSIZE_PIXELS Piksellerde bir ekran nesnesinin yüksekliğini temsil etmek için kullanılan 32 bit imzasız tamsayı.

- VTS_XSIZE_HIMETRIC HIMETRIC birimlerinde bir ekran nesnesinin genişliğini temsil etmek için kullanılan 32 bit imzasız tamsayı.

- VTS_YSIZE_HIMETRIC HIMETRIC birimlerinde bir ekran nesnesinin yüksekliğini temsil etmek için kullanılan 32 bit imzasız tamsayı.

    > [!NOTE]
    >  VTS_FONT ve VTS_PICTURE dışında, varyant veri sabitine işaretçi sağlayan tüm varyant türleri için ek varyant sabitleri tanımlanmıştır. Bu sabitler VTS_P`constantname` kuralı kullanılarak adlandırılır. Örneğin, VTS_PCOLOR VTS_COLOR sabiti için bir işaretçidir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
