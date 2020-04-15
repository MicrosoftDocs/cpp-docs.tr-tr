---
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
ms.openlocfilehash: c8e79f54ed586201a7d82327662643a9a241b8f4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81357275"
---
# <a name="managing-the-state-data-of-mfc-modules"></a>MFC Modüllerinin Durum Verisini Yönetme

Bu makalede, MFC modüllerinin durum verileri ve yürütme akışı (yol kodu yürütücürken bir uygulama üzerinden alır) bir modül girer ve ayrıldığında bu durum nasıl güncelleştirilir tartışır. Modül durumlarının AFX_MANAGE_STATE ve METHOD_PROLOGUE makrolarla değiştirilmesi de tartışılır.

> [!NOTE]
> Buradaki "modül" terimi, yürütülebilir bir programa veya uygulamanın geri kalanından bağımsız olarak çalışan, ancak MFC DLL'nin paylaşılan bir kopyasını kullanan bir DLL (veya DL kümesi) anlamına gelir. ActiveX denetimi, bir modülün tipik bir örneğidir.

Aşağıdaki şekilde gösterildiği gibi, MFC bir uygulamada kullanılan her modül için durum verilerine sahiptir. Bu verilere örnek olarak Windows örnek tanıtıcıları (kaynakları yüklemek `CWinApp` `CWinThread` için kullanılır), bir uygulamanın geçerli ve nesnelerine işaretçiler, OLE modülü başvuru sayıları ve Windows nesne tutamaçları ile Ilgili MFC nesneleri arasındaki bağlantıları koruyan çeşitli haritalar verilebilir. Ancak, bir uygulama birden çok modül kullandığında, her modülün durum verileri uygulama genişliğinde değildir. Bunun yerine, her modülün MFC'nin durum verilerinin kendi özel kopyası vardır.

![Tek bir modülün &#40;uygulama&#41;devlet verileri](../mfc/media/vc387n1.gif "Tek bir modülün devlet verileri &#40;uygulama&#41;") <br/>
Tek Modülün Devlet Verileri (Uygulama)

Bir modülün durum verileri bir yapıda bulunur ve her zaman bu yapıya işaretçi aracılığıyla kullanılabilir. Yürütme akışı aşağıdaki şekilde gösterildiği gibi belirli bir modüle girdiğinde, bu modülün durumu "geçerli" veya "etkili" durum olmalıdır. Bu nedenle, her iş parçacığı nesnesi bu uygulamanın etkili durum yapısıiçin bir işaretçi vardır. Bu işaretçiyi her zaman güncel tutmak, uygulamanın genel durumunu yönetmek ve her modülün durumunun bütünlüğünü korumak için çok önemlidir. Genel durum yanlış yönetimi öngörülemeyen uygulama davranışına yol açabilir.

![Birden çok modülün durum verileri](../mfc/media/vc387n2.gif "Birden çok modülün durum verileri") <br/>
Birden Çok Modülün Durum Verileri

Başka bir deyişle, her modül tüm giriş noktalarında modül durumları arasında doğru geçiş yapmakla yükümlüdür. "Giriş noktası", yürütme akışının modülün kodunu girebileceği herhangi bir yerdir. Giriş noktaları şunlardır:

- [Bir DLL'de dışa aktarılan işlevler](../mfc/exported-dll-function-entry-points.md)

- [COM arabirimlerinin üye işlevleri](../mfc/com-interface-entry-points.md)

- [Pencere yordamları](../mfc/window-procedure-entry-points.md)

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)
