---
title: "İzlenecek yol: Proje (C++) hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- projects [C++], debugging
- project debugging [C++]
- debugging projects
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ec7a363d3aa4601e33e44d15fbb3d667c3a87db4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="walkthrough-debugging-a-project-c"></a>İzlenecek Yol: Proje Hatalarını Ayıklama (C++)
Bu kılavuzda, projeyi test edildiğinde, keşfedilen sorunu düzeltmek üzere programı değiştirin.  
  
## <a name="prerequisites"></a>Önkoşullar  
  
-   Bu kılavuz, C++ dil temelleri anladığınızı varsayar.  
  
-   Ayrıca listelenen ilgili daha önce izlenecek tamamladığınızı varsaymaktadır [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### <a name="to-fix-a-program-that-has-a-bug"></a>Bir hata olan bir program düzeltmek için  
  
1.  Neler görmek için bir `Cardgame` nesnesi yok, yıkıcı için görüntüleme `Cardgame` sınıfı.  
  
     Menü çubuğunda seçin **Görünüm**, **sınıf görünümü**.  
  
     İçinde **sınıf görünümü** penceresinde genişletin **oyun** proje ağacı ve select **Cardgame** sınıfı yöntemleri ve sınıf üyeleri görüntülemek için.  
  
     Kısayol menüsünü açın **~Cardgame(void)** yıkıcı ve ardından **Tanıma Git**.  
  
2.  Azaltmak için `totalParticipants` bir Cardgame sonlandırıldığında açılış ve kapanış köşeli parantez, arasında aşağıdaki kodu ekleyin `Cardgame::~Cardgame` yıkıcı.  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]  
  
3.  Değiştirdikten sonra Cardgame.cpp dosyası şuna benzemelidir:  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]  
  
4.  Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
5.  Yapı tamamlandığında çalıştırın hata ayıklama modunda seçerek **hata ayıklama**, **hata ayıklamayı Başlat** menü çubuğunda ya da F5 tuşuna seçerek. Program ilk kesme noktasında duraklatır.  
  
6.  Menü çubuğunda, program aracılığıyla adım tercih **hata ayıklama**, **Step Over**, veya F10 anahtarı seçin.  
  
     Her Cardgame Oluşturucusu yürütüldükten sonra değerini dikkat `totalParticipants` artırır. Zaman `PlayGames` her Cardgame örneği kapsamının dışına gider ve silinir (ve yıkıcı adlı gibi), döndürür, işlev `totalParticipants` azaltır. Hemen önce `return` deyimi yürütüldüğünde, `totalParticipants` 0'a eşit.  
  
7.  Çıkana kadar programımı adımlarken devam veya seçerek çalışmasına izin **hata ayıklama**, **çalıştırmak** menü çubuğunda ya da F5 tuşuna seçerek.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 **Önceki:** [izlenecek yol: Proje (C++) sınama](../ide/walkthrough-testing-a-project-cpp.md) &#124; **Sonraki:**[izlenecek yol: programınızı (C++) dağıtma](../ide/walkthrough-deploying-your-program-cpp.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C/C++ programları oluşturma](../build/building-c-cpp-programs.md)