---
description: 'Daha fazla bilgi edinin: çeviri: Tanılama'
title: 'Çeviri: Tanılamalar'
ms.date: 11/04/2016
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
ms.openlocfilehash: 09fc44dea8d51dbb267d402745c8c2a095b969d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243061"
---
# <a name="translation-diagnostics"></a>Çeviri: Tanılamalar

**ANSI 2.1.1.3** Bir tanılama nasıl tanımlanır

Microsoft C şu şekilde hata iletileri oluşturur:

> *dosya adı* **(** *satır numarası* **):** *Tanılama* **C**<em>numarası</em> *iletisi*

Burada *dosya adı* , hatanın karşılaştığı kaynak dosyanın adıdır; *satır numarası* , derleyicinin hatayı algıladığı satır numarasıdır; *tanı* "hata" ya da "uyarı"; *sayı* , hata veya uyarıyı tanımlayan benzersiz dört basamaklı bir sayıdır (söz dizimi içinde belirtilen bir **C** tarafından). *ileti* açıklayıcı bir iletidir.

## <a name="see-also"></a>Ayrıca bkz.

[Uygulama tanımlı davranış](../c-language/implementation-defined-behavior.md)
