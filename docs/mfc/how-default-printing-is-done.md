---
description: 'Daha fazla bilgi edinin: varsayılan yazdırma işlemi nasıl yapılır?'
title: Varsayılan Yazdırmayı Yapma
ms.date: 11/04/2016
helpviewer_keywords:
- default printing
- printing [MFC], default
- defaults, printing
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
ms.openlocfilehash: cd2be6cea4e038775f2134dfde434580839d0280
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172875"
---
# <a name="how-default-printing-is-done"></a>Varsayılan Yazdırmayı Yapma

Bu makalede, Windows 'da MFC çerçevesi açısından varsayılan yazdırma süreci açıklanmaktadır.

MFC uygulamalarında, görünüm sınıfının `OnDraw` tüm çizim kodunu içeren adlı bir üye işlevi vardır. `OnDraw` bir [CDC](reference/cdc-class.md) nesnesine parametre olarak bir işaretçi alır. Bu `CDC` nesne tarafından üretilen görüntünün alınacağı cihaz bağlamını temsil eder `OnDraw` . Belgeyi görüntüleyen pencere [WM_PAINT](/windows/win32/gdi/wm-paint) bir ileti aldığında, çerçeve `OnDraw` Bu aygıtı ( [CPaintDC](reference/cpaintdc-class.md) nesnesi) için bir cihaz bağlamı çağırır ve geçirir. Buna uygun olarak, `OnDraw` çıkış ekrana gider.

Windows için programlama bölümünde, çıktıyı yazıcıya göndermek ekrana çıktı göndermeye çok benzer. Bunun nedeni, Windows grafik cihaz arabirimi (GDI) donanımdan bağımsızdır. Ekran görüntüsü için aynı GDI işlevlerini veya yalnızca uygun cihaz bağlamını kullanarak yazdırma için kullanabilirsiniz. `CDC`Alan nesnesi, `OnDraw` yazıcıyı temsil ediyorsa, `OnDraw` Çıkış yazıcıya gider.

Bu, MFC uygulamalarının, sizin bölümlük üzerinde fazladan efor gerekmeden nasıl basit bir yazdırma gerçekleştirebileceğini açıklar. Çerçeve, Yazdır iletişim kutusunu görüntülemeyi ve yazıcı için bir cihaz bağlamı oluşturmayı üstlenir. Kullanıcı, Dosya menüsünden Yazdır komutunu seçtiğinde, bu cihaz bağlamını üzerine geçirir `OnDraw` ve belgeyi yazıcıya çizer.

Ancak, yazdırma ve ekran görüntüleme arasında bazı önemli farklılıklar vardır. Yazdırdığınızda, belgeyi ayrı sayfalara bölmeniz ve bir pencerede hangi bölümün görünür olduğunu göstermek yerine onları birer birer görüntüetmeniz gerekir. Bir eş olarak, kağıdın boyutunu (harf boyutu, yasal boyut veya zarf) bilmeniz gerekir. Yatay veya dikey mod gibi farklı yönlerle yazdırmak isteyebilirsiniz. Microsoft Foundation Class Kitaplığı, uygulamanızın bu sorunları nasıl işleyeceğini tahmin edemeyecektir. bu nedenle, bu özellikleri eklemeniz için bir protokol sağlar.

Bu protokol, çok [sayfalı belgeler](multipage-documents.md)makalesinde açıklanmaktadır.

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma](printing.md)
