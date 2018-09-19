---
title: __based dilbilgisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43e9074de25d8cb914432123478f5f338ff4ba1e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103775"
---
# <a name="based-grammar"></a>__based Dilbilgisi

## <a name="microsoft-specific"></a>Microsoft'a Özgü

Tabanlı Adresleme (statik ve dinamik tabanlı veriler) nesne ayrılmış segment üzerinde kesin denetim gerektiğinde yararlıdır.

Tabanlı adresleme 32-bit ve 64 bit derlemelerde kabul edilebilir "temel bir işaretçi üzerinde" yalnızca formun tanımlayan bir 32 bit veya 64-bit öteleme 32 bit veya 64-bit tabana içeriyor veya temel bir tür **void**.

## <a name="grammar"></a>Dilbilgisi

*temel-aralık-modifier*: **__based (***temel ifade***)** 

*temel ifade*: *based-variablebased-abstract-declaratorsegment-namesegment-cast*

*bağlı değişken*: *tanımlayıcısı*

*temel-Özet-declarator*: *soyut bildirimci*

*temel türü*: *tür adı*

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Tabanlı İşaretçiler](../cpp/based-pointers-cpp.md)