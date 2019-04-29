---
title: 'İzlenecek yol: (C++) projeyi test etme'
ms.date: 04/25/2019
helpviewer_keywords:
- project testing [C++]
- testing projects
- projects [C++], testing
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
ms.openlocfilehash: aa1af9cd355265214827527b986b8602a25e93f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349208"
---
# <a name="walkthrough-testing-a-project-c"></a>İzlenecek yol: (C++) projeyi test etme

Bir programı hata ayıklama modunda çalıştırdığınızda, değişkenlerin ve nesnelerin durumunu incelemek için programı duraklatmak üzere kesme noktaları kullanabilirsiniz.

Bu izlenecek yolda, program çalışırken bir değişkenin değerini izleyin ve neden beklediğiniz değer olmayan türetme.

## <a name="prerequisites"></a>Önkoşullar

- Bu izlenecek yol, C++ dili temellerini anladığınızı varsayar.

- Ayrıca, listelenen önceki izlenecek yolları tamamladığınız varsayılır [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

### <a name="to-run-a-program-in-debug-mode"></a>Bir programı hata ayıklama modunda çalıştırmak için

1. Games.cpp düzenleme için açın.

1. Bu kod satırı seçin:

   `Cardgame.solitaire(1);`

1. Menü çubuğunda, o satıra bir kesme noktası ayarlamak isterseniz **hata ayıklama** > **iki durumlu kesme noktası**, ya da seçin **F9** anahtarı. Satırın solunda kırmızı bir daire görünür; Bu, bir kesme noktasının ayarlandığını belirtir. Bir kesme noktasını kaldırmak için menü komutunu seçebilirsiniz veya **F9** yeniden anahtar.

   Fare kullanıyorsanız, ayarlama veya sol kenar boşluğunu tıklayarak kesme noktası kaldırın.

1. Menü çubuğunda, **hata ayıklama** > **hata ayıklamayı Başlat**, ya da seçin **F5** anahtarı.

   Program kesme noktasına sahip bir satıra ulaştığında, programınız kesme modunda olduğundan yürütme geçici olarak durur. Bir kod satırının solunda bir sarı ok yürütülecek sonraki satırı olduğunu gösterir.

1. Değerini incelemek için `Cardgame::totalParticipants` değişkeni, işaretçiyi `Cardgame` taşıyın araç ipucu penceresinin sol konumunda genişletme denetiminin üzerine. Değişken adı `totalParticipants` ve değeri **12** görüntülenir.

   Kısayol menüsünü açın `Cardgame::totalParticipants` değişkeni seçip **Gözcü Ekle** bu değişkeni görüntülenecek **Watch 1** penceresi. Ayrıca bir değişken vurgulayın ve sürükleyin **Watch 1** penceresi.

1. Menü çubuğunda, kodun sonraki satırına adım tercih **hata ayıklama** > **Step Over**, ya da seçin **F10** anahtarı.

   Değerini `Cardgame::totalParticipants` içinde **Watch 1** penceresi olarak görüntülenen artık **13**.

1. Kısayol menüsünü açın `return 0;` deyimi seçip **imlece kadar Çalıştır**. Kodun sol tarafındaki sarı ok yürütülecek sonraki deyimi işaret eder.

1. `Cardgame::totalParticipants` Sayısı ne zaman azalmalıdır bir `Cardgame` sona erer. Bu noktada, `Cardgame::totalParticipants` 0 olduğundan eşit olmalı tüm `Cardgame` örnekleri silinmiş, ancak **Watch 1** penceresini gösterir `Cardgame::totalparticipants` eşittir **18**. Algılama ve düzeltme sonraki izlenecek yolu tamamlayarak, kodda bir hata olduğunu fark gösteren [izlenecek yol: Bir proje (C++) hata ayıklama](../ide/walkthrough-debugging-a-project-cpp.md).

1. Menü çubuğunda, programı durdurmak için seçin **hata ayıklama** > **hata ayıklamayı Durdur**, ya da seçin **Shift**+**F5**klavye kısayol.

## <a name="next-steps"></a>Sonraki Adımlar

**Önceki:** [İzlenecek yol: Proje Derleme (C++)](../ide/walkthrough-building-a-project-cpp.md)<br/>
**Sonraki:** [İzlenecek yol: Proje Hatalarını Ayıklama (C++)](../ide/walkthrough-debugging-a-project-cpp.md)<br/>

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)<br/>
