---
title: C Ek İşleçleri
ms.date: 10/18/2018
helpviewer_keywords:
- usual arithmetic conversions
- operators [C], addition
- + operator, additive operators
- additive operators
- arithmetic operators [C++], additive operators
ms.assetid: bb8ac205-b061-41fc-8dd4-dab87c8b900c
ms.openlocfilehash: 29bea87e56aa90a8deab7ad7280b3fbdfb45c82b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326917"
---
# <a name="c-additive-operators"></a>C Ek İşleçleri

Ek işleçlerini eklenmesini gerçekleştirme (**+**) ve çıkarma (**-**).

## <a name="syntax"></a>Sözdizimi

*additive-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çarpma ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*additive-expression* **+** *çarpma ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*additive-expression* **-** *çarpma ifadesi*

> [!NOTE]
> Ancak söz diziminin *additive-expression* içerir *ifade çarpma*, bu ifadeleri kullanarak çarpma gerekli olduğunu göstermez. Aşağıdaki sözdizimine bakın [C dili sözdizimi özeti](../c-language/c-language-syntax-summary.md), için *ifade çarpma*, *atama ifadesini*, ve *tekli ifade*.

İşlenen, tamsayı veya kayan değer olabilir. Bazı ek işlemler her işlecinin tartışma altında belirtildiği gibi işaretçi değerleri üzerinde de gerçekleştirilebilir.

Ek işleçlerini olağan aritmetik dönüştürmeler integral ve kayan işlenenler üzerinde gerçekleştirin. Sonuç türü dönüştürme işleminden sonra işlenenler türüdür. Toplama işleçleri tarafından gerçekleştirilen dönüştürmeler taşma veya yetersiz kalma koşulları sağlamaz olduğundan, dönüştürme işleminden sonra bir toplama işleminin sonucu işlenenler türünü temsil edilemiyorsa bilgiler kaybolabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Ek İşleçler: + and -](../cpp/additive-operators-plus-and.md)
