---
title: Önceki Visual C++ Sürümü Projelerini Yükseltme
ms.date: 11/04/2016
helpviewer_keywords:
- 32-bit code porting
- upgrading Visual C++ applications, 32-bit code
ms.assetid: 18cdacaa-4742-43db-9e4c-2d9e73d8cc84
ms.openlocfilehash: dcbec57c75b4dc6fb72a3b35040e12cab0e7111e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740869"
---
# <a name="upgrading-projects-from-earlier-versions-of-visual-c"></a>Önceki Visual C++ Sürümü Projelerini Yükseltme

Çoğu durumda, Visual Studio'nun önceki bir sürümde oluşturulmuş bir projeyi açabilirsiniz. Ancak, Visual Studio bunu yapabilmek için projeyi yükseltir. Bu yükseltilmiş projeyi kaydederseniz önceki sürümde açılamaz.

> [!IMPORTANT]
> Zaten dönüştürülmüş bir projeyi dönüştürmeye çalışırsanız, yeniden dönüştürme sonucunda varolan dosyalar silineceğinden Visual Studio bu işlem için sizden onay ister.

Yükseltilen birçok proje ve çözüm, hiçbir değişikliğe gerek olmadan başarılı bir şekilde oluşturulabilir. Ancak, bazı projeler için ayarları, kaynak kodu veya her ikisini birden değiştirmek gerekebilir. İlk olarak, ayarlarla ilgili sorunları ele almak için aşağıdaki yönergeleri kullanmanızı öneririz; bunun ardından proje yine de oluşturulmazsa, kod sorunlarını ele alabilirsiniz. Daha fazla bilgi için [olası yükseltme sorunlarına genel bakış](../porting/overview-of-potential-upgrade-issues-visual-cpp.md).

1. Varolan projenin ve çözüm dosyalarının bir kopyasını oluşturun. İsterseniz, dosyaların sürümlerini karşılaştırabilmek için geçerli Visual Studio sürümü ile önceki sürümü yan yana yükleyin.

2. Visual Studio'nun geçerli sürümünde projenin veya çözümün kopyasını açın (böylece yükseltmiş olursunuz) ve kaydedin.

3. Dönüştürülen her proje için kısayol menüsünü açın ve seçin **özellikleri**. Altında **yapılandırma özellikleri**seçin **genel** ve ardından **Platform araç takımını**, geçerli sürümü seçin. (Örneğin, Visual Studio 2017 için seçin **v141**.)

4. Çözümü oluşturun. Yapı başarısız olursa ayarları değiştirin ve yeniden derleyin.

Veri kaynaklarında saklı yordamları daha kolay değiştirebilmeniz ve hataları ayıklayabilmeniz için, veri kaynakları ayrı bir veritabanı projesinde yer alır. Veri kaynakları içeren bir C++ projesini yükseltirseniz, ayrı bir veritabanı projesi otomatik olarak oluşturulur.

Hedeflenen Windows sürümlerine yönelik güncelleştirme hakkında daha fazla bilgi için bkz: [değiştirme WINVER ve _WIN32_WINNT](../porting/modifying-winver-and-win32-winnt.md).

## <a name="see-also"></a>Ayrıca bkz.

[Derleme Sistemi Değişiklikleri](../build/build-system-changes.md)<br/>
[Visual Studio 2017'deki Visual C++ Yenilikleri](../what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Visual C++ değişiklik geçmişi 2003 - 2015](../porting/visual-cpp-change-history-2003-2015.md)<br/>
[Standart Olmayan Davranış](../cpp/nonstandard-behavior.md)
