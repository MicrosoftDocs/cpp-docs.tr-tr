---
title: Önceki Visual C++ Sürümü Projelerini Yükseltme
ms.date: 11/04/2016
helpviewer_keywords:
- 32-bit code porting
- upgrading Visual C++ applications, 32-bit code
ms.assetid: 18cdacaa-4742-43db-9e4c-2d9e73d8cc84
ms.openlocfilehash: dae4937661db945fa17f15ea39b0d17a8bf72640
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768230"
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

## <a name="in-this-section"></a>Bu bölümde

[Kodunuzu Evrensel CRT’ye Yükseltme](upgrade-your-code-to-the-universal-crt.md)<br/>
[WINVER ve _WIN32_WINNT'de Değişiklik Yapma](modifying-winver-and-win32-winnt.md)<br/>
[Kitaplık İçeriklerindeki Bağımlılıklarınızı Düzeltme](fix-your-dependencies-on-library-internals.md)<br/>
[Kayan Nokta Geçiş Sorunları](floating-point-migration-issues.md)<br/>
[Visual Studio’da Eski Projeleri Oluşturmak için Yerel Çoklu Sürüm Paketi Kullanma](use-native-multi-targeting.md)<br/>
[Visual Studio 2019 önizlemede kullanım dışı bırakılan Visual C++ özellikleri](features-deprecated-in-visual-studio.md)<br/>
[Derleme Sistemi Değişiklikleri](build-system-changes.md)<br/>

## <a name="see-also"></a>Ayrıca Bkz.

[Visual Studio 2017'deki Visual C++ Yenilikleri](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Visual C++ değişiklik geçmişi 2003 - 2015](../porting/visual-cpp-change-history-2003-2015.md)<br/>
[Standart Olmayan Davranış](../cpp/nonstandard-behavior.md)
