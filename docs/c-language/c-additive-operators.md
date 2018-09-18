---
title: C ek işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- usual arithmetic conversions
- operators [C], addition
- + operator, additive operators
- additive operators
- arithmetic operators [C++], additive operators
ms.assetid: bb8ac205-b061-41fc-8dd4-dab87c8b900c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7be460ace4e407a328c0cf23c9e6c9af09d17ca0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101489"
---
# <a name="c-additive-operators"></a>C Ek İşleçleri

Ek işleçlerini eklenmesini gerçekleştirme (**+**) ve çıkarma (**-**).

## <a name="syntax"></a>Sözdizimi

*additive-expression*: *çarpma ifadesi*

*additive-expression***+***çarpma ifadesi* 

*additive-expression***-***çarpma ifadesi* 

> [!NOTE]
>  Ancak söz diziminin *additive-expression* içerir *ifade çarpma*, bu ifadeleri kullanarak çarpma gerekli olduğunu göstermez. Aşağıdaki sözdizimine bakın [C dili sözdizimi özeti](../c-language/c-language-syntax-summary.md), için *ifade çarpma*, *atama ifadesini*, ve *tekli ifade*.

İşlenen, tamsayı veya kayan değer olabilir. Bazı ek işlemler her işlecinin tartışma altında belirtildiği gibi işaretçi değerleri üzerinde de gerçekleştirilebilir.

Ek işleçlerini olağan aritmetik dönüştürmeler integral ve kayan işlenenler üzerinde gerçekleştirin. Sonuç türü dönüştürme işleminden sonra işlenenler türüdür. Toplama işleçleri tarafından gerçekleştirilen dönüştürmeler taşma veya yetersiz kalma koşulları sağlamaz olduğundan, dönüştürme işleminden sonra bir toplama işleminin sonucu işlenenler türünü temsil edilemiyorsa bilgiler kaybolabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Ek İşleçler: + and -](../cpp/additive-operators-plus-and.md)