---
description: 'Daha fazla bilgi edinin: Çeviri aşamaları'
title: Çeviri aşamaları
ms.date: 08/29/2019
helpviewer_keywords:
- translation phases
- preprocessor, translation
- translation, compiler process
- preprocessor
- file translation [C++], compiler process
- files [C++], translation
ms.assetid: a7f7a8c9-e8ba-4321-9e50-ebfbbdcce9db
ms.openlocfilehash: 6a561fe9aa61df293a038a9edfd094dbdef4fe89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333181"
---
# <a name="phases-of-translation"></a>Çeviri aşamaları

C ve C++ programları, her biri programın bazı metinlerini içeren bir veya daha fazla kaynak dosyadan oluşur. Bir kaynak dosyası, *içerme dosyaları* ile birlikte, ön işlemci yönergesi kullanılarak dahil edilen `#include` , ancak gibi koşullu derleme yönergeleri tarafından kaldırılan kodun bölümlerini dahil olmamak üzere `#if` bir *çeviri birimi* olarak adlandırılır.

Kaynak dosyalar farklı zamanlarda çevrilebilir. Aslında, yalnızca güncel olmayan dosyaları çevirmek yaygındır. Çevrilen çeviri birimleri ayrı nesne dosyalarına veya nesne kodu kitaplıklarına işlenebilir. Bu ayrı, çevrilmiş çeviri birimleri daha sonra yürütülebilir bir program veya dinamik bağlantı kitaplığı (DLL) oluşturacak şekilde bağlanır. Bağlayıcıya giriş olarak kullanılabilecek dosyalar hakkında daha fazla bilgi için bkz. [LINK Input Files](../build/reference/link-input-files.md).

Çeviri birimleri şu kullanılarak iletişim kurabilir:

- Dış bağlantısı olan işlevlere yapılan çağrılar.

- Dış bağlantısı olan sınıf üye işlevlerine yapılan çağrılar.

- Dış bağlantısına sahip nesneleri doğrudan değiştirme.

- Dosyaları doğrudan değiştirme.

- İşlemler arası iletişim (yalnızca Microsoft Windows tabanlı uygulamalar için).

Aşağıdaki listede derleyicinin dosyaları çeviren aşamalar açıklanmaktadır:

*Karakter eşleme*\
Kaynak dosyadaki karakterler iç kaynak gösterimine eşlenir. Trigraf dizileri bu aşamada tek karakterli iç temsilde dönüştürülür.

*Satır splılama*\
Bir ters eğik çizgi ( **\\** ) ile biten ve hemen ardından yeni satır karakteri gelen tüm satırlar, kaynak dosyadaki bir sonraki satıra katılır ve bu da fiziksel satırlardan mantıksal satırlar oluşturulur. Boş olmadığı müddetçe, kaynak dosyanın önünde ters eğik çizgi karakteri olan bir yeni satır karakteriyle bitmesi gerekir.

*Simgeleştirme*\
Kaynak dosya, ön işleme belirteçlerine ve boşluk karakterlerine bölünmüştür. Kaynak dosyadaki yorumların her biri bir boşluk karakteriyle değiştirilmiştir. Yeni satır karakterleri korunur.

*Ön*\
Ön işleme yönergeleri yürütülür ve makrolar kaynak dosyasına genişletilir. `#include`İfade, eklenen herhangi bir metinde önceki üç çeviri adımı ile başlayarak çeviriyi çağırır.

*Karakter kümesi eşleme*\
Tüm kaynak karakter kümesi üyeleri ve kaçış dizileri, yürütme karakter kümesi içindeki eşdeğerlerine dönüştürülür. Microsoft C ve C++ için hem kaynak hem de yürütme karakter kümeleri ASCII 'dir.

*Dize birleştirme*\
Tüm bitişik dize ve geniş dize sabit değerleri birleştirilir. Örneğin, `"String " "concatenation"` olur `"String concatenation"` .

*İde*\
Tüm belirteçler, sözdizimsel ve anlam açısından analiz edilir; Bu belirteçler nesne koduna dönüştürülür.

*'Nın*\
Tüm dış başvurular, yürütülebilir bir program veya dinamik bağlantı kitaplığı oluşturmak için çözümlenir.

Derleyici, söz dizimi hatalarıyla karşılaştığı Çeviri aşamaları sırasında uyarıları veya hataları yayınlar.

Bağlayıcı tüm dış başvuruları çözümler ve standart kitaplıklarla birlikte bir veya daha fazla ayrı işlenen çeviri birimini birleştirerek yürütülebilir bir program veya DLL oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci](../preprocessor/preprocessor.md)
