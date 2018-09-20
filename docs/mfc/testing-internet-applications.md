---
title: Internet uygulamalarını test etme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Web applications [MFC], testing
- debugging Web applications [MFC], testing applications
- testing [MFC], Internet applications
- debugging [MFC], Web applications
- Internet debugging and testing
ms.assetid: ac4c74e3-d4ad-4e19-8f6c-e270de067f01
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 518fbe754b676798c6d2acc2a3e26ea1d3e3d4ac
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444172"
---
# <a name="testing-internet-applications"></a>Internet Uygulamalarını Test Etme

Özellikle bir Web sunucusu üzerinde çalışan uygulamalar için Internet üzerindeki bazı test zorluk vardır. İlk sınamanızda büyük olasılıkla yapılmayacak test sunucusuna bağlanan bir tek kullanıcı istemci kullanarak. Bu, kodunuzu hata ayıklama için yararlı olacaktır.

Gerçek koşullar altında test etmek istersiniz: düşük hızlı seri satırları yanı sıra yüksek hızlı bağlantılar bağlı birden fazla istemciyle modem bağlantıları dahil olmak üzere. Gerçek koşullarının benzetimini yapmak zor olabilir, ancak kesinlikle tasarlama olası senaryolar zaman harcama ve yürütmeden değerindedir. Mümkünse, kapasite ve stres testi araçları kullanmak ayrıca isteyeceksiniz. Hata, zamanlama hataları gibi belirli sınıfları bulmak ve yeniden oluşturmak için zordur.

Internet programlamayı zorlukları görünürlüğü biridir. Sitenizde çok sayıda erişim, sunucuyu yavaşlatabilir. Sunucunuzu düzgün bir şekilde kullanmanız gerekir. Uygulamanız (örneğin, veri bozulması kayıt defterine yazarken veya istemcide tanımlama bilgilerini yazılırken) başarısız olursa, bir kullanıcının bilgisayarına zararlı olabilecek herhangi bir şey önlemek isteyebilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Internet Programlama Görevleri](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)

