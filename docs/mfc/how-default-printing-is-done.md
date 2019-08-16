---
title: Varsayılan Yazdırmayı Yapma
ms.date: 11/04/2016
helpviewer_keywords:
- default printing
- printing [MFC], default
- defaults, printing
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
ms.openlocfilehash: 5019bcad769c4b7cdb699facef145a21d9b5e11c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508426"
---
# <a name="how-default-printing-is-done"></a>Varsayılan Yazdırmayı Yapma

Bu makalede, Windows 'da MFC çerçevesi açısından varsayılan yazdırma süreci açıklanmaktadır.

MFC uygulamalarında, görünüm sınıfının tüm çizim kodunu içeren adlı `OnDraw` bir üye işlevi vardır. `OnDraw`bir [CDC](../mfc/reference/cdc-class.md) nesnesine parametre olarak bir işaretçi alır. Bu `CDC` nesne tarafından `OnDraw`üretilen görüntünün alınacağı cihaz bağlamını temsil eder. Belgeyi görüntüleyen pencere bir [WM_PAINT](/windows/win32/gdi/wm-paint) iletisi aldığında, çerçeve bu uygulamayı ekran için bir `OnDraw` cihaz bağlamı (belirli bir [CPaintDC](../mfc/reference/cpaintdc-class.md) nesnesi) ile çağırır ve geçirir. Buna uygun `OnDraw`olarak, çıkış ekrana gider.

Windows için programlama bölümünde, çıktıyı yazıcıya göndermek ekrana çıktı göndermeye çok benzer. Bunun nedeni, Windows grafik cihaz arabirimi (GDI) donanımdan bağımsızdır. Ekran görüntüsü için aynı GDI işlevlerini veya yalnızca uygun cihaz bağlamını kullanarak yazdırma için kullanabilirsiniz. Alan nesnesi, yazıcıyı temsil ediyorsa, `OnDraw`çıkış yazıcıya gider. `CDC` `OnDraw`

Bu, MFC uygulamalarının, sizin bölümlük üzerinde fazladan efor gerekmeden nasıl basit bir yazdırma gerçekleştirebileceğini açıklar. Çerçeve, Yazdır iletişim kutusunu görüntülemeyi ve yazıcı için bir cihaz bağlamı oluşturmayı üstlenir. Kullanıcı, Dosya menüsünden Yazdır komutunu seçtiğinde, bu cihaz bağlamını üzerine `OnDraw`geçirir ve belgeyi yazıcıya çizer.

Ancak, yazdırma ve ekran görüntüleme arasında bazı önemli farklılıklar vardır. Yazdırdığınızda, belgeyi ayrı sayfalara bölmeniz ve bir pencerede hangi bölümün görünür olduğunu göstermek yerine onları birer birer görüntüetmeniz gerekir. Bir eş olarak, kağıdın boyutunu (harf boyutu, yasal boyut veya zarf) bilmeniz gerekir. Yatay veya dikey mod gibi farklı yönlerle yazdırmak isteyebilirsiniz. Microsoft Foundation Class Kitaplığı, uygulamanızın bu sorunları nasıl işleyeceğini tahmin edemeyecektir. bu nedenle, bu özellikleri eklemeniz için bir protokol sağlar.

Bu protokol, çok [sayfalı belgeler](../mfc/multipage-documents.md)makalesinde açıklanmaktadır.

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma](../mfc/printing.md)
