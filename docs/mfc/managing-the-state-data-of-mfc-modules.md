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
ms.openlocfilehash: d1bed6f3b0dddf0d4ae5e8309d683e52c9e82410
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52174898"
---
# <a name="managing-the-state-data-of-mfc-modules"></a>MFC Modüllerinin Durum Verisini Yönetme

Bu makalede durumu verilerini MFC modülleri ve bu durum akışını (yol kod aracılığıyla uygulama yürütülürken sürer) girer ve bir modül bırakır nasıl güncelleştirileceğini açıklar. Modül durumları AFX_MANAGE_STATE ve METHOD_PROLOGUE makroları ile değiştirmeyi de ele alınmıştır.

> [!NOTE]
>  Terim "modülünü" Buraya yürütülebilir bir program veya bir DLL (veya dll) uygulama geri kalanı bağımsız olarak çalışan başvuruyor, ancak paylaşılan MFC DLL kopyasını kullanır. ActiveX denetimi, bir modül tipik bir örneğidir.

Aşağıdaki resimde gösterildiği gibi MFC durumu verilerini bir uygulamada kullanılan her bir modül için vardır. Bu verileri örnekler Windows örneği tutamaçlarını (kaynaklarını yüklemek için kullanılan), geçerli işaretçileri `CWinApp` ve `CWinThread` bir uygulama, OLE modül başvuru sayılarını ve bağlantıları arasında eşlemeler çeşitli nesneleri Windows tanıtıcıları ve karşılık gelen MFC nesnelerin örneklerini nesne. Bir uygulama birden çok modül kullandığında, ancak her modülün durumu verilerini uygulama değil geniş. Bunun yerine, modüllerin, kendi özel MFC'nin durumu verilerini kopyasına sahip olur.

![Durum verileri tek bir modülün &#40;uygulama&#41;](../mfc/media/vc387n1.gif "durum verileri tek bir modülün &#40;uygulama&#41;") <br/>
Durum verilerinin tek bir modülün (uygulama)

Bir modülün durumu verilerini bir yapıda yer alır ve bu yapıya bir işaretçi aracılığıyla her zaman kullanılabilir. Aşağıdaki resimde gösterildiği gibi yürütmenin akışını belirli bir modülün girdiğinde, bu modülün durumu "geçerli" veya "etkin" durumunda olması gerekir. Bu nedenle, her iş parçacığı nesnesi, uygulamanın geçerli durumu yapısına bir işaretçi var. Bu işaretçinin en güncel tutma kez uygulamanın genel durumunu yönetme ve her modülün durumu bütünlüğünü korumak için önemli. Genel durum, yanlış yönetim edilmesi öngörülemeyen uygulama davranışına neden olabilir.

![Durum verileri birden çok modül](../mfc/media/vc387n2.gif "verilerin birden çok modül durumu") <br/>
Birden çok modüllerinin durum verisini

Diğer bir deyişle, her Modülü doğru şekilde kendi giriş noktalarının hiç modül durumları arasında geçiş yapmak için sorumludur. Bir "Giriş", yürütmenin akışını modülün kod girebileceğiniz herhangi bir yerde noktasıdır. Giriş noktaları şunlardır:

- [DLL'de dışa aktarılan işlevleri](../mfc/exported-dll-function-entry-points.md)

- [COM arabirimlerinin üye işlevleri](../mfc/com-interface-entry-points.md)

- [Pencere yordamları](../mfc/window-procedure-entry-points.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)
