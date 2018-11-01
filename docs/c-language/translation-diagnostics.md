---
title: 'Çeviri: Tanılamalar'
ms.date: 11/04/2016
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
ms.openlocfilehash: 4863b97dc1db7ff295b5f786ca97da2551d0fa62
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665003"
---
# <a name="translation-diagnostics"></a>Çeviri: Tanılamalar

**ANSI 2.1.1.3** bir tanılama nasıl tanımlanır

Microsoft C şu şekilde hata iletileri oluşturur:

> *filename* **(** *satır numarası* **):** *tanılama* **C**  <em>sayı</em> *iletisi*

Burada *filename* içinde hata ile karşılaşıldı; kaynak dosyasının adıdır *satır numarası* derleyici; hata algılandı satır numarası *tanılama* "error" ya da "uyarı"; *numarası* benzersiz bir dört basamaklı sayıdır (önünde bir **C**sözdiziminde belirtildiği gibi) hata veya uyarı; tanımlar *ileti* açıklayıcı bir iletidir.

## <a name="see-also"></a>Ayrıca Bkz.

[Uygulama Tanımlı Davranış](../c-language/implementation-defined-behavior.md)