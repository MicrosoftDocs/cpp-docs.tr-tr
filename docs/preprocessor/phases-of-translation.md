---
title: Çeviri aşamaları | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- translation phases
- preprocessor, translation
- translation, compiler process
- preprocessor
- file translation [C++], compiler process
- files [C++], translation
ms.assetid: a7f7a8c9-e8ba-4321-9e50-ebfbbdcce9db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b72e861b2639b8cf1e2cdf8293461cb8b1a00813
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808744"
---
# <a name="phases-of-translation"></a>Çeviri Aşamaları

C ve C++ programları, her biri bazı program metni içeren bir veya daha fazla kaynak dosyadan oluşur. İçerme dosyaları ile birlikte bir kaynak dosyası (kullanarak dahil olan dosyaları `#include` önişlemci yönergesi) ancak gibi koşullu derleme yönergeleri tarafından kaldırılan kod bölümlerini dahil değil `#if`, bir "çeviri birimini." olarak adlandırılır

Kaynak dosyaları farklı zamanlarda çevrilmiş — aslında, yalnızca güncel olmayan dosyaları çevirmek için yaygındır. Çevrilmiş çeviri birimleri ayrı nesne dosyaları ya da nesne kodu kitaplıkları işlenebilir. Bu ayrı, çevrilmiş çeviri birimleri yürütülebilir bir program veya bir dinamik bağlantı kitaplığı (DLL) form bağlanır.  Bağlayıcı girişi olarak kullanılabilir dosya hakkında daha fazla bilgi için bkz. [LINK giriş dosyaları](../build/reference/link-input-files.md).

Çeviri birimleri kullanarak iletişim kurabilir:

- Dış bağlantıya sahip işlevlerin çağrıları.

- Dış bağlantıya sahip bir sınıf üyesi işlevleri için çağırır.

- Doğrudan değiştirilmesine nesnelerin dış bağlantısı vardır.

- Dosyaların doğrudan değiştirilmesi.

- İşlemler arası iletişim (Microsoft Windows tabanlı uygulamalar için yalnızca).

Aşağıdaki listede, derleyicinin dosyalarını çevirir aşamaları açıklanmaktadır:

*Karakter Eşleme*<br/>
Kaynak dosyadaki karakter, iç kaynak gösterimine eşlenir. Trigraf dizileri tek karakterli iç gösterimi bu aşamasında dönüştürülür.

*Satır birleştirme*<br/>
Tüm satırların bitiş ters eğik çizgi (**\\**) ve hemen ardından tarafından bir yeni satır karakteri fiziksel satırlar mantıksal satırlarından oluşturan kaynak dosyadaki sonraki satır ile birleştirilir. Boş değilse bir kaynak dosyası içinde bir ters eğik çizgi öncesinde bir yeni satır karakteri bitmelidir.

*Simgeleştirme*<br/>
Kaynak dosyası ön işleme belirteçleri ve boşluk karakterleri olarak ayrılır. Bir boşluk karakteri ile her kaynak dosyasındaki yorumlar değiştirilir. Yeni satır karakterleri korunur.

*Ön işleme*<br/>
Ön işleme yönergeleri yürütülür ve makroları kaynak dosyasına genişletilir. `#include` Deyimi önceki üç çeviri adımları dahil herhangi bir metin ile başlayan çeviri çağırır.

*Karakter kümesi eşleme*<br/>
Tüm kaynak karakter kümesi üyeleri ve kaçış dizileri yürütme karakter kümesindeki eşdeğerlerine dönüştürülür. Microsoft C ve C++ için hem kaynak hem de yürütme karakter kümesi ASCII'dir.

*Dize birleştirme*<br/>
Tüm bitişik dize ve geniş dize değişmez değerleri sıralanır. Örneğin, `"String " "concatenation"` olur `"String concatenation"`.

*Çeviri*<br/>
Tüm belirteçlerin sözdizimsel olarak ve anlamsal olarak analiz edilir; Bu belirteçler, nesne koda dönüştürülür.

*Bağlantı*<br/>
Tüm dış başvuruları, yürütülebilir bir program veya bir dinamik bağlantı kitaplığı oluşturmaya çözümlenir.

Derleyici, sözdizimi hataları bulduğu çeviri aşamaları sırasında bir uyarı veya hata verir.

Bağlayıcının dış başvuruları çözümleniyor ve bir araya getirerek bir yürütülebilir programı veya DLL oluşturur veya daha fazla standart kitaplıkları birlikte çeviri birimleri ayrı olarak işlenir.

## <a name="see-also"></a>Ayrıca Bkz.

[Ön İşlemci](../preprocessor/preprocessor.md)