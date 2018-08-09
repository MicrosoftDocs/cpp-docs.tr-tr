---
title: 'İzlenecek yol: standart bir C++ programını (C++) oluşturma | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vcfirstapp
- vccreatefirst
dev_langs:
- C++
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4f3f01ab95237a0401394d429443804ce65a4385
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017334"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>İzlenecek yol: standart bir C++ programını (C++) oluşturma
Standart C++ programlar oluşturmak için Visual Studio tümleşik geliştirme ortamında (IDE) Visual C++ kullanabilirsiniz. Bu kılavuzda açıklanan adımları izleyerek, bir proje oluşturun, projeye yeni bir dosya ekleyin, C++ kodu eklemek ve ardından derleyin ve program kullanarak çalıştırmak için dosyasını değiştirin [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
 Kendi C++ programınızı yazabilir veya örnek programlardan birini kullanın. Bu kılavuzda örnek program bir konsol uygulamasıdır. Bu uygulamanın kullandığı `set` C++ Standart Kitaplığı'nda kapsayıcı.  
  
 Uygun Visual C++ 2003 C++ standardı ile şu büyük özel durumlar: iki aşamalı ad arama, özel durum belirtimleri ve dışarı aktarma. Ayrıca, Visual C++ birkaç C ++ 0 x özelliklerini, örneğin, lambdas, otomatik, static_assert, rvalue başvuruları ve extern şablonları destekler.  
  
> [!NOTE]
>  Standart ile uyumluluk gerekliyse kullanın `/Za` Microsoft uzantılarını standart devre dışı bırakma derleyici seçeneği. Daha fazla bilgi için [/Za, /Ze (dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu adım adım öğreticiyi tamamlamak için C++ dilinin temellerini anlamanız gerekir.  
  
### <a name="to-create-a-project-and-add-a-source-file"></a>Bir proje oluşturun ve bir kaynak dosyası eklemek için  
  
1.  İşaret ederek bir proje oluşturma **yeni** üzerinde **dosya** menüsüne ve ardından **proje**.  
  
2.  İçinde **Visual C++** Proje Türleri bölmesinde ye **Windows Masaüstü**ve ardından **Windows konsol uygulaması**.  
  
3.  Proje için bir ad yazın.  
  
     Varsayılan olarak, projeyi içeren çözüm proje ile aynı ada sahiptir ancak farklı bir ad yazabilirsiniz. Proje için farklı bir konum da yazabilirsiniz.  
  
     Tıklayın **Tamam** projeyi oluşturmak için.  
  
4.  Varsa **Çözüm Gezgini** , görüntülenmiyorsa **görünümü** menüsünde tıklatın **Çözüm Gezgini**.  
  
5.  Yeni bir kaynak dosyası projeye aşağıdaki şekilde ekleyin.  
  
    1.  İçinde **Çözüm Gezgini**, sağ **kaynak dosyaları** klasörünü **Ekle**ve ardından **yeni öğe**.  
  
    2.  İçinde **kod** düğümünü tıklatın **C++ dosyası (.cpp)** dosyası için bir ad yazın ve ardından **Ekle**.  
  
     .Cpp dosyası görünür **kaynak dosyaları** klasöründe **Çözüm Gezgini**, ve dosya Visual Studio Düzenleyicisi'nde açılır.  
  
6.  Düzenleyicideki dosyada, C++ Standart Kitaplığı'nı kullanan geçerli bir C++ programınızı yazabilir veya örnek programlardan birini kopyalayın ve dosyaya yapıştırın.  
  
7.  Dosyayı kaydedin.  
  
8. Üzerinde **derleme** menüsünde tıklatın **Çözümü Derle**.  
  
     **Çıkış** penceresi, örneğin, konumunu yapı günlüğüne ve yapı durumunu belirten bir ileti gibi derleme ilerlemesi hakkında bilgileri görüntüler.  
  
9. Üzerinde **hata ayıklama** menüsünü tıklatın **hata ayıklama olmadan Başlat**.  
  
     Örnek programı kullandıysanız bir komut penceresi görüntülenir ve kümede belirli tamsayılar bulunup bulunmadığını gösterir.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 **Önceki:** [konsol uygulamaları Visual C++'ta](../windows/console-applications-in-visual-cpp.md). **Sonraki:**[izlenecek yol: komut satırında yerel C++ programı derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)