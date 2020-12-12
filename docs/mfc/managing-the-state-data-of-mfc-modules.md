---
description: 'Hakkında daha fazla bilgi edinin: MFC modüllerinin durum verilerini yönetme'
title: MFC Modüllerinin Durum Verisini Yönetme
ms.date: 11/19/2018
helpviewer_keywords:
- global state [MFC]
- data management [MFC], MFC modules
- window procedure entry points [MFC]
- exported interfaces and global state [MFC]
- module states [MFC], saving and restoring
- data management [MFC]
- MFC, managing state data
- multiple modules [MFC]
- module state restored [MFC]
ms.assetid: 81889c11-0101-4a66-ab3c-f81cf199e1bb
ms.openlocfilehash: e991e73b40f49f3be4630c26957c827aa6f1bf0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228033"
---
# <a name="managing-the-state-data-of-mfc-modules"></a>MFC Modüllerinin Durum Verisini Yönetme

Bu makalede, MFC modüllerinin durum verileri ve yürütme akışı (yürütülürken yol kodu bir uygulamadan geçer) bir modüle girdiğinde ve ayrıldığında bu durumun nasıl güncelleştirildiği açıklanır. Modül durumlarının AFX_MANAGE_STATE ve METHOD_PROLOGUE makrolarıyla değiştirilmesi de ele alınmıştır.

> [!NOTE]
> Burada "Module" terimi, uygulamanın geri kalanından bağımsız olarak çalışan, ancak MFC DLL 'inin paylaşılan bir kopyasını kullanan bir çalıştırılabilir programa veya DLL 'ye (veya dll kümesine) başvurur. Bir ActiveX denetimi bir modülün tipik bir örneğidir.

Aşağıdaki şekilde gösterildiği gibi, MFC bir uygulamada kullanılan her modül için durum verileri içerir. Bu verilere örnek olarak, Windows örnek tutamaçları (kaynak yükleme için kullanılır), `CWinApp` bir uygulamanın geçerli ve nesnelerine yönelik işaretçiler, `CWinThread` OLE modülü başvuru sayıları ve Windows nesne tutamaçları ile buna KARŞıLıK gelen MFC nesnelerinin örnekleri arasındaki bağlantıları koruyacak çeşitli haritalar sayılabilir. Ancak, bir uygulama birden çok modül kullandığında, her modülün durum verileri uygulama genelinde değildir. Bunun yerine, her modülün kendi özel MFC durum verileri kopyası vardır.

![Tek bir modülün uygulama&#41;durum verileri &#40;](../mfc/media/vc387n1.gif "Tek bir modülün uygulama&#41; durum verileri &#40;") <br/>
Tek bir modülün durum verileri (uygulama)

Modülün durum verileri bir yapıda bulunur ve her zaman bu yapıya yönelik bir işaretçi aracılığıyla kullanılabilir. Yürütmenin akışı, aşağıdaki şekilde gösterildiği gibi belirli bir modüle girdiğinde, söz konusu modülün durumu "geçerli" veya "etkin" durum olmalıdır. Bu nedenle, her iş parçacığı nesnesinin, uygulamanın etkin durum yapısına yönelik bir işaretçisi vardır. Bu işaretçinin her zaman güncel tutulması, uygulamanın genel durumunu yönetmek ve her modülün durumunun bütünlüğünü sürdürmek için önemlidir. Genel durumun yanlış yönetimi öngörülemeyen uygulama davranışına neden olabilir.

![Birden çok modülün durum verileri](../mfc/media/vc387n2.gif "Birden çok modülün durum verileri") <br/>
Birden çok modülün durum verileri

Diğer bir deyişle, her modül tüm giriş noktalarında modül durumları arasında doğru geçiş yapmaktan sorumludur. "Giriş noktası", yürütme akışının modülün kodunu girebileceği bir yerdir. Giriş noktaları şunları içerir:

- [DLL 'de aktarılmış işlevler](exported-dll-function-entry-points.md)

- [COM arabirimlerinin üye işlevleri](com-interface-entry-points.md)

- [Pencere yordamları](window-procedure-entry-points.md)

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC konuları](general-mfc-topics.md)
