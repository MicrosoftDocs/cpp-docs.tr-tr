---
description: 'Hakkında daha fazla bilgi edinin: Framework kodunuzu nasıl çağırır'
title: Framework'ün Kodunuzu Çağırması
ms.date: 11/04/2016
helpviewer_keywords:
- control flow [MFC], MFC framework and your code
- events [MFC], command routing in MFC
- command routing [MFC], framework
- command handling [MFC], calling handlers and code in MFC
- events [MFC], event-driven programming
- MFC, calling code from
- MFC, calling code
- application-specific events [MFC]
- command routing [MFC], MFC
ms.assetid: 39e68189-a580-40d0-9e35-bf5cd24a8ecf
ms.openlocfilehash: eebc431d8ba4d0edf7eddfe113d6f6559087be70
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290381"
---
# <a name="how-the-framework-calls-your-code"></a>Framework'ün Kodunuzu Çağırması

Kaynak kodunuz ve MFC çerçevesindeki kod arasındaki ilişkiyi anlamak çok önemlidir. Uygulamanız çalıştırıldığında, denetim akışının çoğu Framework kodunda bulunur. Framework, kullanıcının komutları seçtiği ve bir görünümdeki verileri düzenlediğini Windows 'dan iletileri alan ileti döngüsünü yönetir. Framework 'ün kendisi tarafından işleyebileceği olaylar, kodunuza hiçbir şekilde güvenmez. Örneğin Framework, Windows 'un nasıl kapatılmasını ve Kullanıcı komutlarına yanıt olarak uygulamadan nasıl çıkacağını bilir. Bu görevleri işlediği için Framework, size bu olaylara yanıt vermek için ileti işleyicileri ve C++ sanal işlevlerini kullanır. Kodunuz denetimde değil; ancak Framework.

Çerçeve uygulamaya özgü olaylar için kodunuzu çağırır. Örneğin, Kullanıcı bir menü komutu seçtiğinde, Framework komutu bir C++ nesneleri dizisi boyunca yönlendirir: geçerli görünüm ve çerçeve penceresi, görünümle ilişkili belge, belgenin belge şablonu ve uygulama nesnesi. Bu nesnelerden biri komutu işleyebiliyorsanız, uygun ileti işleyicisi işlevini çağırarak bunu yapar. Verilen herhangi bir komut için, çağrılan kod sizinki olabilir veya Framework 'ün olabilir.

Bu düzenleme, Windows veya olay odaklı programlama için geleneksel programlama ile karşılaşılan programcılar için biraz tanıdık gelecektir.

İlgili konularda, Framework 'ün ne yaptığını okur ve uygulamayı çalıştırır ve ardından uygulama sonlandırıldığında temizler. Yazdığınız kodun nerede olduğunu da anlayacaksınız.

Daha fazla bilgi için bkz. [sınıf CWinApp: uygulama sınıfı](cwinapp-the-application-class.md) ve [Belge şablonları ve belge/görünüm oluşturma işlemi](document-templates-and-the-document-view-creation-process.md).

## <a name="see-also"></a>Ayrıca bkz.

[Çerçevede derleme](building-on-the-framework.md)
