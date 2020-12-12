---
description: 'Hakkında daha fazla bilgi edinin: değişken parametre türü sabitleri'
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
ms.openlocfilehash: 5bc3dcc8a0a888b21b88700db99b05c0f12a4c5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218504"
---
# <a name="variant-parameter-type-constants"></a>Değişken Parametre Türü Sabitleri

Bu konuda, Microsoft Foundation Class Kitaplığı OLE denetim sınıflarıyla kullanılmak üzere tasarlanan değişken parametre türlerini gösteren yeni sabitler listelenmiştir.

Aşağıda, sınıf sabitlerinin bir listesi verilmiştir:

## <a name="variant-data-constants"></a><a name="_mfc_variant_data_constants"></a> Değişken veri sabitleri

- Bir RGB renk değerini göstermek için kullanılan 32 bitlik bir tamsayı VTS_COLOR.

- `IFontDisp`OLE yazı tipi nesnesinin arabirimine bir işaretçi vts_font.

- Bir Windows tanıtıcı değeri VTS_HANDLE.

- `IPictureDisp`OLE resim nesnesinin arabirimine bir işaretçi VTS_PICTURE.

- Radyo düğmeleri gibi Denetimler grubunda kullanılması amaçlanan bir denetim için kullanılan 16 bitlik bir değer VTS_OPTEXCLUSIVE. Bu tür, kapsayıcıda bir denetimin doğru bir değere sahip olması durumunda, diğerlerinin FALSE olması gerektiğini belirtir.

- Üç olası değerden (seçili, temizlenmiş, kullanılamayan) birine (örneğin, bir onay kutusu) sahip olabilecek özellikler için kullanılan 16 bit işaretli bir tamsayı VTS_TRISTATE.

- HIMETRIK birimlerde x ekseninde bir konumu temsil etmek için kullanılan 32 bitlik işaretsiz bir tamsayı VTS_XPOS_HIMETRIC.

- HIMETRIK birimlerde y ekseni üzerinde bir konumu temsil etmek için kullanılan 32 bitlik işaretsiz bir tamsayı VTS_YPOS_HIMETRIC.

- X eksenindeki bir konumu piksel cinsinden göstermek için kullanılan 32 bitlik işaretsiz bir tamsayı VTS_XPOS_PIXELS.

- Y ekseni üzerindeki bir konumu piksel cinsinden göstermek için kullanılan 32 bitlik işaretsiz bir tamsayı VTS_YPOS_PIXELS.

- Piksel cinsinden bir ekran nesnesinin genişliğini temsil etmek için kullanılan 32 bitlik işaretsiz bir tamsayı VTS_XSIZE_PIXELS.

- Bir ekran nesnesinin yüksekliğini piksel cinsinden temsil etmek için kullanılan 32 bitlik işaretsiz bir tamsayı VTS_YSIZE_PIXELS.

- HIMETRIK birimlerde bir ekran nesnesinin genişliğini temsil etmek için kullanılan 32 bitlik işaretsiz bir tamsayı VTS_XSIZE_HIMETRIC.

- HIMETRIK birimlerde bir ekran nesnesinin yüksekliğini temsil etmek için kullanılan 32 bitlik işaretsiz bir tamsayı VTS_YSIZE_HIMETRIC.

    > [!NOTE]
    >  Değişken veri sabitine bir işaretçi sağlayan VTS_FONT ve VTS_PICTURE dışında tüm değişken türleri için ek değişken sabitleri tanımlanmıştır. Bu sabitler VTS_P kuralı kullanılarak adlandırılmaktadır `constantname` . Örneğin, VTS_PCOLOR VTS_COLOR sabiti için bir işaretçidir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
