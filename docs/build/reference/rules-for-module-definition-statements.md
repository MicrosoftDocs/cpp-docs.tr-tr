---
title: Modül Tanımlama Deyimleri Kuralları
ms.date: 11/04/2016
f1_keywords:
- .def
helpviewer_keywords:
- module definition files, statement syntax
- module definition files
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
ms.openlocfilehash: f6269ad2d5bf3952e485f2ca5e5d1f411c5f1e0c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318517"
---
# <a name="rules-for-module-definition-statements"></a>Modül Tanımlama Deyimleri Kuralları

.Def dosyası içindeki tüm deyimler için aşağıdaki sözdizimi kurallarını uygulayın. Belirli ifadeler için geçerli olan diğer kuralları her deyimiyle açıklanmaktadır.

- Deyimler, öznitelik anahtar sözcükleri ve kullanıcı tarafından belirtilen tanımlayıcıları büyük/küçük harfe duyarlıdır.

- Uzun dosya adları boşluk veya noktalı virgül (;) içeren tırnak işaretleri (") içine alınması gerekir.

- Bir veya daha fazla boşluk, sekme veya yeni satır karakterleri deyimi anahtar sözcüğü, bağımsız değişkenlerden ayırmak ve ifadeleri birbirinden ayırmak için kullanın. İki nokta üst üste (:) veya belirten bir bağımsız değişken eşittir (=) sıfır veya daha fazla boşluk, sekme veya yeni satır karakteri tarafından çevrelenir.

- A **adı** veya **Kitaplığı** deyimi kullandıysanız gelmelidir diğer deyimler.

- **Bölümleri** ve **dışarı AKTARMALARI** deyimleri .def dosyasında birden çok kez görüntülenebilir. Her deyim bir veya daha fazla boşluk, sekme veya yeni satır karakteri tarafından ayrılmalıdır birden çok belirtimleri alabilir. Deyimi anahtar sözcüğü ilk belirtimi önce bir kez görünmesi gerekir ve her ek belirtimi önce yinelenebilir.

- Fazla sayıda deyim eşdeğer bağlantı komut satırı seçeneği sunulur. Ek ayrıntılar için karşılık gelen bağlantı seçeneği açıklamasına bakın.

- .Def dosyasında açıklamaları noktalı virgül (;) tarafından belirlenmiş her satırının başında. Bir yorum bir satır içeren bir ifade paylaşım yapamazsınız, ancak çok satırlı bir deyimde özellikleri arasında yer alabilir. (**Bölümleri** ve **dışarı AKTARMALARI** çok satırlı deyimleri.)

- Belirtilen taban 10 ya da onaltılık sayısal bağımsız değişkenler.

- Bir dize bağımsız değişkeni eşleşmesi durumunda bir [ayrılmış sözcük](reserved-words.md), çift tırnak işaretleri (") içine alınması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Modül-Tanımlama (.Def) Dosyaları](module-definition-dot-def-files.md)
