---
title: Varsayılan Yazdırmayı Yapma
ms.date: 11/04/2016
helpviewer_keywords:
- default printing
- printing [MFC], default
- defaults, printing
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
ms.openlocfilehash: 8fb47aadd2389438f8d2f48a26cd3aea8d871d81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518982"
---
# <a name="how-default-printing-is-done"></a>Varsayılan Yazdırmayı Yapma

Bu makalede, Windows, varsayılan yazdırma işlemi MFC çerçevesi açısından açıklanmaktadır.

MFC uygulamalarında adında bir üye işlev view sınıfında `OnDraw` , tüm çizim kodunu içerir. `OnDraw` için bir işaretçi alır bir [CDC](../mfc/reference/cdc-class.md) bir parametre olarak nesne. Olduğunu `CDC` nesnesi tarafından oluşturulan görüntüyü almak için cihaz bağlamı temsil eder `OnDraw`. Belge görüntüleme penceresi aldığında bir [WM_PAINT](/windows/desktop/gdi/wm-paint) iletisi, framework çağrıları `OnDraw` ve bunu bir ekran için bir cihaz bağlamı geçirir (bir [CPaintDC](../mfc/reference/cpaintdc-class.md) belirli nesnesi). Buna `OnDraw`gelecek çıkış ekranına.

Windows programlamada, yazıcı gönderen çıkışına ekrana çıkış göndermeye benzer. Windows grafik cihaz arabirimi (GDI) donanımdan bağımsız olmasıdır. Uygun bir cihaz bağlamı kullanarak, yazdırma veya ekran için aynı GDI işlevleri kullanabilirsiniz. Varsa `CDC` nesnesinin `OnDraw` alır yazıcı temsil `OnDraw`gelecek çıkışını yazıcıya.

Bu, sizin için fazladan çaba gerektirmeden MFC uygulamaları basit yazdırma nasıl gerçekleştireceğinizi açıklar. Framework Yazdır iletişim kutusunu görüntüleme ve yazıcı için bir cihaz bağlamı oluşturma üstlenir. Kullanıcı Dosya menüsünden Yazdır komutunu seçtiğinde, bu cihaz bağlamına görünümü geçirir `OnDraw`, yazıcıda belge çizer.

Ancak, yazdırma ve ekran görüntüsü arasındaki önemli bazı farklar vardır. Yazdırırken, farklı sayfaları ve bunları teker teker hangi kısmını görüntülemek yerine görünür bir pencerede görünen belge bölmek zorunda. Bir corollary (letter boyutu, geçerli boyut veya Zarf olup) kağıt boyutu farkında olmanız gerekir. Yatay veya dikey modu gibi farklı yönleri yazdırma isteyebilirsiniz. Microsoft Foundation Class Kitaplığı, bir protokol bu özellikleri eklemenize olanak sağlar, böylece uygulamanız bu sorunları nasıl işleyeceğini tahmin edemezsiniz.

Protokol makalesinde açıklanan [çok sayfalı belgeleri](../mfc/multipage-documents.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Yazdırma](../mfc/printing.md)

