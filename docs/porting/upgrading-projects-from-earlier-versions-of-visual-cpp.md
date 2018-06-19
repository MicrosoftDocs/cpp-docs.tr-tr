---
title: Önceki Visual C++ sürümü projelerini yükseltme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 32-bit code porting
- upgrading Visual C++ applications, 32-bit code
ms.assetid: 18cdacaa-4742-43db-9e4c-2d9e73d8cc84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c503a2feae728c67507bf80db6eb2c5dabc3252f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849736"
---
# <a name="upgrading-projects-from-earlier-versions-of-visual-c"></a>Önceki Visual C++ Sürümü Projelerini Yükseltme
Çoğu durumda, Visual Studio'nun önceki bir sürümde oluşturulmuş bir proje açabilirsiniz. Ancak, Visual Studio bunu yapabilmek için projeyi yükseltir. Bu yükseltilmiş projeyi kaydederseniz önceki sürümde açılamaz.  
  
> [!IMPORTANT]
>  Zaten dönüştürülmüş bir projeyi dönüştürmeye çalışırsanız, yeniden dönüştürme sonucunda varolan dosyalar silineceğinden Visual Studio bu işlem için sizden onay ister.  
  
 Yükseltilen birçok proje ve çözüm, hiçbir değişikliğe gerek olmadan başarılı bir şekilde oluşturulabilir. Ancak, bazı projeler için ayarları, kaynak kodu veya her ikisini birden değiştirmek gerekebilir. İlk olarak, ayarlarla ilgili sorunları ele almak için aşağıdaki yönergeleri kullanmanızı öneririz; bunun ardından proje yine de oluşturulmazsa, kod sorunlarını ele alabilirsiniz. Daha fazla bilgi için bkz: [olası yükseltme sorunlarını genel bakış](../porting/overview-of-potential-upgrade-issues-visual-cpp.md).  
  
1.  Varolan projenin ve çözüm dosyalarının bir kopyasını oluşturun. İsterseniz, dosyaların sürümlerini karşılaştırabilmek için geçerli Visual Studio sürümü ile önceki sürümü yan yana yükleyin.  
  
2.  Visual Studio'nun geçerli sürümünde projenin veya çözümün kopyasını açın (böylece yükseltmiş olursunuz) ve kaydedin.  
  
3.  Dönüştürülen her proje için kısayol menüsünü açın ve seçin **özellikleri**. Altında **yapılandırma özellikleri**seçin **genel** ve ardından **Platform araç takımı**, geçerli sürümü seçin. (Örneğin, Visual Studio 2017 v141 seçin.)  
  
4.  Çözümü oluşturun. Yapı başarısız olursa ayarları değiştirin ve yeniden derleyin.  
  
 Veri kaynaklarında saklı yordamları daha kolay değiştirebilmeniz ve hataları ayıklayabilmeniz için, veri kaynakları ayrı bir veritabanı projesinde yer alır. Veri kaynakları içeren bir C++ projesini yükseltirseniz, ayrı bir veritabanı projesi otomatik olarak oluşturulur.  
  
 Güncelleştirme hedeflenen Windows sürümleri hakkında daha fazla bilgi için bkz: [değiştirme WINVER ve _WIN32_WINNT](../porting/modifying-winver-and-win32-winnt.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme Sistemi Değişiklikleri](../build/build-system-changes.md)  
 [Visual Studio 2017'de Visual C++ için Yenilikler](../what-s-new-for-visual-cpp-in-visual-studio.md) [Visual C++ değişiklik geçmişini 2003 2015](../porting/visual-cpp-change-history-2003-2015.md)   
 [Standart Olmayan Davranış](../cpp/nonstandard-behavior.md)