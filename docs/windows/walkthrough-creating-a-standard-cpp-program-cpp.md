---
title: "İzlenecek yol: bir standart C++ programı (C++) oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
f1_keywords:
- vcfirstapp
- vccreatefirst
dev_langs: C++
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
caps.latest.revision: "36"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 67b44b8f21f2c8deea7cd6b9c89e87004e088d63
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>İzlenecek yol: bir standart C++ programı (C++) oluşturma
Visual C++, Visual Studio tümleşik geliştirme ortamı (IDE) standart C++ programları oluşturmak için kullanabilirsiniz. Bu izlenecek adımları izleyerek, bir proje oluşturun, projeye yeni bir dosya ekleyin, C++ kodu ekleyin ve ardından derlemek ve program kullanarak çalıştırmak için dosyasını değiştirmek [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
 Kendi C++ programı yazın veya örnek programlar birini kullanın. Bu kılavuzda örnek bir konsol uygulaması programdır. Bu uygulamanın kullandığı `set` C++ Standart Kitaplığı kapsayıcısında.  
  
 Visual C++ uyumlu 2003 C++ standart ana bu özel durumları ile birlikte: iki aşamalı ad arama, özel durum belirtimleri ve dışarı aktarma. Ayrıca, Visual C++, örneğin, Lambda'lar, otomatik, static_assert, rvalue başvuru ve extern şablonları birkaç C ++ 0 x özelliklerini destekler.  
  
> [!NOTE]
>  Standart uyumluluk gerekiyorsa kullanın **/Za** standart için Microsoft uzantıları devre dışı bırakma derleyici seçeneği. Daha fazla bilgi için bkz: [/Za, /Ze (dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu adım adım öğreticiyi tamamlamak için C++ dilinin temellerini anlamanız gerekir.  
  
### <a name="to-create-a-project-and-add-a-source-file"></a>Proje oluşturma ve kaynak dosyası eklemek için  
  
1.  Proje göstererek oluşturma **yeni** üzerinde **dosya** menüsüne ve ardından **proje**.  
  
2.  İçinde **Visual C++** Proje Türleri bölmesinde, tıklatın **Win32**ve ardından **Win32 konsol uygulaması**.  
  
3.  Proje için bir ad yazın.  
  
     Varsayılan olarak, projeyi içeren çözümü projesi olarak aynı ada sahip, ancak farklı bir ad yazın. Proje için farklı bir konum da yazabilirsiniz.  
  
     Tıklatın **Tamam** projesi oluşturmak için.  
  
4.  İçinde **Win32 Uygulama Sihirbazı'nı**, tıklatın **sonraki**seçin **boş proje**ve ardından **son**.  
  
5.  Varsa **Çözüm Gezgini** üzerinde görüntülenmiyorsa **Görünüm** menüsünde tıklatın **Çözüm Gezgini**.  
  
6.  Yeni bir kaynak dosyası projeye aşağıdaki şekilde ekleyin.  
  
    1.  İçinde **Çözüm Gezgini**, sağ **kaynak dosyaları** klasörünü **Ekle**ve ardından **yeni öğe**.  
  
    2.  İçinde **kod** düğümü tıklatın **C++ dosyasına (.cpp)**, dosya için bir ad yazın ve ardından **Ekle**.  
  
     Kaynak dosyaları klasöründe .cpp dosya görünür **Çözüm Gezgini**, ve dosya Visual Studio düzenleyicisinde açılır.  
  
7.  Dosyayı düzenleyicide C++ Standart Kitaplığı kullanan geçerli bir C++ programı yazın veya örnek programlar birini kopyalayın ve dosyaya yapıştırın.  
  
8.  Dosyayı kaydedin.  
  
9. Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
     **Çıkış** penceresi derleme ilerleme durumu, örneğin, derleme günlüğünde ve yapı durumu bildiren bir ileti konumu ile ilgili bilgileri görüntüler.  
  
10. Üzerinde **hata ayıklama** menüsünde tıklatın **Başlat hata ayıklama olmadan**.  
  
     Örnek program kullandıysanız, bir komut penceresi görüntülenir ve belirli tamsayılar kümesinde bulunan olup olmadığını gösterir.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 **Önceki:** [konsol uygulamaları Visual C++'ta](../windows/console-applications-in-visual-cpp.md). **Sonraki:**[izlenecek yol: komut satırında yerel C++ programı derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)