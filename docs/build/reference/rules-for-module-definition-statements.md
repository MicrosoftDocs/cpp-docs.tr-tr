---
description: 'Hakkında daha fazla bilgi edinin: Module-Definition deyimleri için kurallar'
title: Modül Tanımlama Deyimleri Kuralları
ms.date: 11/04/2016
f1_keywords:
- .def
helpviewer_keywords:
- module definition files, statement syntax
- module definition files
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
ms.openlocfilehash: bca1f279a9a93690edeaabc2264d1cfe869b3e80
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225004"
---
# <a name="rules-for-module-definition-statements"></a>Modül Tanımlama Deyimleri Kuralları

Aşağıdaki söz dizimi kuralları bir. def dosyasındaki tüm deyimler için geçerlidir. Belirli deyimler için uygulanan diğer kurallar her bir deyim ile açıklanmıştır.

- Deyimler, öznitelik anahtar sözcükleri ve Kullanıcı tarafından belirtilen tanımlayıcılar büyük/küçük harfe duyarlıdır.

- Boşluk veya noktalı virgül içeren uzun dosya adları (;) tırnak işaretleri (") içine alınmalıdır.

- Bir deyim anahtar sözcüğünü bağımsız değişkenlerinden ayırmak ve deyimlerden ayırmak için bir veya daha fazla boşluk, sekme veya yeni satır karakteri kullanın. İki nokta (:) ya da bir bağımsız değişkeni atayan eşittir işareti (=) sıfır veya daha fazla boşluk, sekme veya yeni satır karakteri ile çevrelenmiş.

- Bir **ad** veya **kitaplık** deyimi kullanılırsa, diğer tüm deyimlerden önce gelmelidir.

- **Bölümler** ve **dışarı aktarmalar** deyimleri. def dosyasında birden çok kez bulunabilir. Her bir ifade, bir veya daha fazla boşluk, sekme veya yeni satır karakteri ile ayrılması gereken birden çok belirtim alabilir. Deyimin anahtar sözcüğü, ilk belirtiden önce bir kez görünmelidir ve her ek belirtiden önce tekrarlanabilir.

- Birçok deyimin karşılık gelen bir bağlantı komut satırı seçeneği vardır. Ek ayrıntılar için karşılık gelen bağlantı seçeneğinin açıklamasına bakın.

- . Def dosyasındaki açıklamalar noktalı virgülle atanır (;) Her yorum satırının başlangıcında. Yorum bir satırı bir ifadesiyle paylaşamaz, ancak bir çok satırlı ifadede belirtimler arasında görünebilir. (**Bölümler** ve **dışarı aktarmalar** çok satırlı deyimlerdir.)

- Sayısal bağımsız değişkenler taban 10 veya onaltılı olarak belirtilir.

- Bir dize bağımsız değişkeni ayrılmış bir [sözcükle](reserved-words.md)eşleşiyorsa, çift tırnak işareti (") içine alınmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Modül tanımı (. Def) dosyaları](module-definition-dot-def-files.md)
