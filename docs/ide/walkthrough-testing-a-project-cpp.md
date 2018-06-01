---
title: 'İzlenecek yol: Proje (C++) test etme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- project testing [C++]
- testing projects
- projects [C++], testing
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a9455fa9bf3c9f903f5018a1263978913aa35b2
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33333570"
---
# <a name="walkthrough-testing-a-project-c"></a>İzlenecek Yol: Projeyi Test Etme (C++)
Bir program hata ayıklama modunda çalıştırdığınızda, değişkenler ve nesnelerin durumunu incelemek için programı duraklatmak için kesme noktaları kullanabilirsiniz.  
  
 Bu kılavuzda, program çalışırken bir değişkenin değerini izleyebilir ve beklediğiniz değerdir neden türetme.  
  
## <a name="prerequisites"></a>Önkoşullar  
  
-   Bu kılavuz, C++ dil temelleri anladığınızı varsayar.  
  
-   Ayrıca listelenen ilgili daha önce izlenecek tamamladığınızı varsaymaktadır [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### <a name="to-run-a-program-in-debug-mode"></a>Hata ayıklama modunda bir programı çalıştırmak için  
  
1.  TestGames.cpp düzenlemek için açın.  
  
2.  Bu kod satırı seçin:  
  
     `Cardgame.solitaire(1);`  
  
3.  Menü çubuğunda, o satırdaki bir kesme noktası belirleyerek tercih **hata ayıklama**, **kesme**, veya F9 anahtarı seçin. Kırmızı bir daire satırının sol görünür; Bu, bir kesme noktası ayarlandığını gösterir. Bir kesme noktası kaldırmak için menü komutunu veya F9 anahtarı yeniden seçebilirsiniz.  
  
     Fare kullanıyorsanız, ayarlama veya bir kesme noktası sol kenar boşluğunda tıklatarak kaldırın.  
  
4.  Menü çubuğunda seçin **hata ayıklama**, **hata ayıklamayı Başlat**, veya F5 tuşuna seçin.  
  
     Program kesme sahip satır ulaştığında, yürütme programınızı kesme modunda olduğu için geçici olarak durdurur. Bir kod satırı solundaki sarı bir ok yürütülecek sonraki satıra olduğunu gösterir.  
  
5.  Değerini incelemek için `Cardgame::totalParticipants` değişkeni işaretçiyi `Cardgame` ve ardından üzerine getirin, bu araç ipucu penceresinin sol genişletme denetim. Değişken adı `totalParticipants` ve 12 değeri görüntülenir.  
  
     Kısayol menüsünü açın `Cardgame::totalParticipants` değişkeni ve ardından **Gözcü Ekle** o değişkende görüntülenecek **izleme 1** penceresi. Ayrıca bir değişken seçin ve sürükleyin **izleme 1** penceresi.  
  
6.  Kodun sonraki satırında, menü çubuğunda, adım tercih **hata ayıklama**, **Step Over**, veya F10 anahtarı seçin.  
  
     Değeri `Cardgame::totalParticipants` içinde **izleme 1** penceresi artık 13 görüntülenir.  
  
7.  Kısayol menüsünü açın `return 0;` deyimi ve ardından **çalıştırmak için imleç**. Sonraki deyim yürütülebilecek kod noktaları soluna sarı oku.  
  
8.  `Cardgame::totalParticipants` Kaç bir Cardgame sonlandırıldığında azaltın. Bu noktada, `Cardgame::totalParticipants` Cardgame hepsinin silinmiş olduğundan 0 eşit olmalıdır ancak **izleme 1** penceresi gösterir `Cardgame::totalparticipants` 18'e eşittir. Bu algılama ve düzeltme sonraki Kılavuzu izleyerek, kodda bir hata olduğunu gösterir [izlenecek yol: bir proje (C++) hata ayıklama](../ide/walkthrough-debugging-a-project-cpp.md).  
  
9. Menü çubuğunda, programı durdurmak için tercih **hata ayıklama**, **durdurma hata ayıklama**, veya Shift + F5 klavye kısayolu seçin.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 **Önceki:** [izlenecek yol: Proje derleme (C++)](../ide/walkthrough-building-a-project-cpp.md) &#124; **sonraki:**[izlenecek yol: bir projenin (C++)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)