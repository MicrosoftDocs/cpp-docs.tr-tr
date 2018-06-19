---
title: Dil anahtar sözcükleri (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keywords [C++]
ms.assetid: 021013b2-70ac-4df9-aa77-4af1c67a1a67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 241205ad25314034d8d36fa7ad1b156b13080fd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33134419"
---
# <a name="language-keywords-ccli"></a>Dil Anahtar Sözcükleri (C++/CLI)
Visual C++ için C++ için Yönetilen Uzantılar'dan değiştirilen çeşitli dil anahtar sözcükleri.  
  
 Yeni Visual C++ sözdiziminde tüm anahtar sözcükleri önekten olarak çift alt çizgi kaldırılır (tek bir istisna: `__identifier` tutulur). Örneğin, bir özelliği şimdi olarak bildirilmiş `property`değil `__property`.  
  
 Yönetilen Uzantılar'çift alt çizgi önek kullanarak iki birincil nedeni vardı:  
  
-   Bu yerel uzantılara ISO-C++ Standart sağlama uyumluluğunu yöntemdir. Yeni anahtar sözcüklerin ve belirteçleri gibi standart dil ile uyumsuzlukları değil tanıtmak için Yönetilen Uzantılar tasarımının birincil amacı oluştu. Bu nedenle, işaretçi sözdizimi için yönetilen başvuru türündeki nesnelerin bildirimi seçimi motive büyük bölümü içindeydi.  
  
-   Kılması dışında çift alt çizgi de bozucu dil kullanıcılarının varolan kod tabanıyla olma makul bir garanti kullanımıdır. Yönetilen Uzantılar tasarımı ikinci birincil amacı, bu.  
  
 Çift alt çizgi kaldırma tüm Microsoft uyumlu olmaya kararlı kalır. Ancak, yeni ve güçlü bir programlama modeli CLR dinamik Nesne modelini gösteren desteği. Bu yeni kip desteği, kendi üst düzey anahtar sözcükleri ve belirteçleri gerektirir. Bu tümleştirme ve standart dili desteklerken sırasında bu yeni kip birinci sınıf bir ifade sağlamak Aranan. Yeni sözdizimi tasarımı bu iki farklı nesne modeline birinci sınıf bir programlama deneyimi sağlar.  
  
 Benzer şekilde, bu yeni dil anahtar bozucu yapısını en üst düzeye çıkarma ile ilgilenen duyuyoruz. Bu bağlamsal ya da aralıklı anahtar kullanımı ile gerçekleştirilir. Biz gerçek yeni dil sözdizimine göz önce bu iki özel anahtar sözcüğü özellikleri anlamlı deneyelim.  
  
 Bağlamsal anahtar sözcüğü belirli program bağlamları içinde özel bir anlamı yoktur. Genel program için içinde `sealed` normal bir tanımlayıcı olarak kabul edilir. Ancak, yönetilen başvuru sınıf türü bildirimi kısmı içinde oluştuğunda, bu sınıf bildirimi bağlamında bir anahtar olarak kabul edilir. Bu en aza indiren yeni bir anahtar sözcük dilde bir şey Tanıtımı olası bozucu etkisini, varolan bir kod tabanına sahip kullanıcılar için çok önemli eşitleyerek. Aynı anda ek dil özelliğinin - Yönetilen Uzantılar ile mümkün olmayan bir şey birinci sınıf bir deneyim sağlamak kullanıcıların yeni işlevsellik sağlar. Bir örnek için nasıl `sealed` kullanılan bkz [bir yönetilen sınıf türü bildirimi](../dotnet/declaration-of-a-managed-class-type.md).  
  
 Aralıklı bir anahtar kelime gibi `value class`, bağlamsal bir anahtar sözcük özel bir durumdur. Varolan bir anahtar sözcük, boşlukla ayrılmış bir bağlamsal değiştirici ile çiftleri. Çift tek bir birim olarak yerine iki ayrı anahtar olarak kabul edilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C + +/ CLI geçiş öncüsü](../dotnet/cpp-cli-migration-primer.md)   
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)