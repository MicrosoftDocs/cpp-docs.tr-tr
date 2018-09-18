---
title: 'Çeviri: Tanılamalar | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d297cfd4f4dee49d3344ae2f159f85682f05ea2f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017592"
---
# <a name="translation-diagnostics"></a>Çeviri: Tanılamalar

**ANSI 2.1.1.3** bir tanılama nasıl tanımlanır

Microsoft C şu şekilde hata iletileri oluşturur:

> *filename* **(** *satır numarası* **):** *tanılama* **C**  <em>sayı</em> *iletisi*

Burada *filename* içinde hata ile karşılaşıldı; kaynak dosyasının adıdır *satır numarası* derleyici; hata algılandı satır numarası *tanılama* "error" ya da "uyarı"; *numarası* benzersiz bir dört basamaklı sayıdır (önünde bir **C**sözdiziminde belirtildiği gibi) hata veya uyarı; tanımlar *ileti* açıklayıcı bir iletidir.

## <a name="see-also"></a>Ayrıca Bkz.

[Uygulama Tanımlı Davranış](../c-language/implementation-defined-behavior.md)