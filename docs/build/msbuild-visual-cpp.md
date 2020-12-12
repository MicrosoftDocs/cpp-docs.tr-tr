---
description: Hakkında daha fazla bilgi için bkz. komut satırında MSBuild-C++
title: Komut satırında MSBuild-C++
ms.date: 12/12/2018
helpviewer_keywords:
- MSBuild
ms.assetid: 7a1be7ff-0312-4669-adf2-5f5bf507d560
ms.openlocfilehash: 9d78c50b398b0ad97cfd75727fdb4219677c546b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179856"
---
# <a name="msbuild-on-the-command-line---c"></a>Komut satırında MSBuild-C++

Genel olarak, proje özelliklerini ayarlamak ve MSBuild sistemini çağırmak için Visual Studio kullanmanızı öneririz. Ancak, **MSBuild** aracını doğrudan komut isteminden kullanabilirsiniz. Yapı işlemi, oluşturabileceğiniz ve düzenleyebileceğiniz bir proje dosyasındaki (. vcxproj) bilgiler tarafından denetlenir. Proje dosyası derleme aşamalarını, koşullarını ve olaylarını temel alan derleme seçeneklerini belirtir. Ayrıca, sıfır veya daha fazla komut satırı *seçeneği* bağımsız değişkeni de belirtebilirsiniz.

> **msbuild.exe** [ *project_file* ] [ *Seçenekler* ]

Proje dosyasında belirtilen belirli özellikleri ve hedefleri geçersiz kılmak için **/target** (veya **/t**) ve **/Property** (veya **/p**) komut satırı seçeneklerini kullanın.

Proje dosyasının önemli bir işlevi, projenize uygulanan belirli bir işlem olan bir *hedef* ve bu işlemi gerçekleştirmek için gereken giriş ve çıkışları belirtmektir. Proje dosyası bir veya daha fazla hedefi belirtebilir ve bu, varsayılan bir hedef içerebilir.

Her hedef bir veya daha fazla *görev* dizisinden oluşur. Her görev, bir çalıştırılabilir komut içeren bir .NET Framework sınıfı tarafından temsil edilir. Örneğin, [CL görevi](/visualstudio/msbuild/cl-task) [cl.exe](reference/compiling-a-c-cpp-program.md) komutunu içerir.

*Görev parametresi* , sınıf görevinin bir özelliğidir ve genellikle çalıştırılabilir komutun bir komut satırı seçeneğini temsil eder. Örneğin, `FavorSizeOrSpeed` `CL` görevin parametresi **/OS** ve **/ot** derleyici seçeneklerine karşılık gelir.

Ek görev parametreleri MSBuild altyapısını destekler. Örneğin, `Sources` görev parametresi diğer görevler tarafından tüketilen bir görev kümesini belirtir. MSBuild görevleri hakkında daha fazla bilgi için bkz. [görev başvurusu](/visualstudio/msbuild/msbuild-task-reference).

Çoğu görev, dosya adları, yollar ve dize, sayısal veya Boole parametreleri gibi giriş ve çıkış gerektirir. Örneğin, ortak bir giriş, Derlenecek bir. cpp kaynak dosyasının adıdır. Önemli bir giriş parametresi, derleme yapılandırmasını ve platformunu belirten bir dizedir; Örneğin, "Debug \| Win32". Girişler ve çıktılar, bir öğesinde içerilen bir veya daha fazla Kullanıcı tanımlı XML `Item` öğesi tarafından belirtilir `ItemGroup` .

Proje dosyası, Kullanıcı tanımlı *Özellikler* ve `ItemDefinitionGroup` *öğeler* de belirtebilir. Yapıda değişkenler olarak kullanılabilecek özellikler ve öğeler form adı/değer çiftleri. Bir çiftin ad bileşeni bir *makroyu* tanımlar ve değer bileşeni *makro değerini* bildirir. Bir özellik makrosunda $ (*ad*) gösterimi kullanılarak erişilir ve bir öğe makrosunda%(*ad*) gösterimi kullanılarak erişilir.

Bir proje dosyasındaki diğer XML öğeleri, makroları test edebilir ve ardından herhangi bir makronun değerini koşullu olarak ayarlayabilir veya yapı yürütmesini denetleyebilir. Makro adları ve sabit dizeler, yol ve dosya adı gibi yapılar oluşturmak için birleştirilebilir. Komut satırında, **/Property** seçeneği bir proje özelliğini ayarlar veya geçersiz kılar. Komut satırında öğelere başvurulamaz.

MSBuild sistemi, bir hedefi başka bir hedeften önce veya sonra koşullu olarak yürütebilir. Ayrıca sistem, hedefin kullandığı dosyaların, gösterdiği dosyalardan daha yeni olup olmadığına bağlı olarak bir hedef oluşturabilir.

MSBuild hakkında daha fazla bilgi için bkz.

- [MSBuild](/visualstudio/msbuild/msbuild) MSBuild kavramlarına genel bakış.

- [MSBuild başvurusu](/visualstudio/msbuild/msbuild-reference) MSBuild sistemiyle ilgili başvuru bilgileri.

- [Proje dosyası şema başvurusu](/visualstudio/msbuild/msbuild-project-file-schema-reference) MSBuild XML şema öğelerini öznitelikleri ve üst ve alt öğeleri ile birlikte listeler. Özellikle [ItemGroup](/visualstudio/msbuild/itemgroup-element-msbuild), [PropertyGroup](/visualstudio/msbuild/propertygroup-element-msbuild), [target](/visualstudio/msbuild/target-element-msbuild)ve [Task](/visualstudio/msbuild/task-element-msbuild) öğelerine göz önünde.

- [Komut satırı başvurusu](/visualstudio/msbuild/msbuild-command-line-reference) msbuild.exe ile kullanabileceğiniz komut satırı bağımsız değişkenlerini ve seçeneklerini açıklar.

- [Görev başvurusu](/visualstudio/msbuild/msbuild-task-reference) MSBuild görevlerini açıklar. Özellikle Visual C++ özgü olan bu görevleri unutmayın: [BSCMAKE görevi](/visualstudio/msbuild/bscmake-task), [CL görevi](/visualstudio/msbuild/cl-task), [CPPClean görevi](/visualstudio/msbuild/cppclean-task), [LIB görevi](/visualstudio/msbuild/lib-task), [bağlantı görevi](/visualstudio/msbuild/link-task), [MIDL](/visualstudio/msbuild/midl-task)görevi, [MT görevi](/visualstudio/msbuild/mt-task), [RC görevi](/visualstudio/msbuild/rc-task), [SetEnv Görevi](/visualstudio/msbuild/setenv-task), [VCMessage görevi](/visualstudio/msbuild/vcmessage-task)

## <a name="in-this-section"></a>Bu Bölümde

|Süre|Tanım|
|----------|----------------|
|[İzlenecek yol: C++ projesi oluşturmak için MSBuild kullanma](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)|**MSBuild** kullanarak Visual Studio C++ projesi oluşturmayı gösterir.|
|[Nasıl yapılır: MSBuild projelerinde derleme olaylarını kullanma](how-to-use-build-events-in-msbuild-projects.md)|Yapı başlamadan önce, derlemede bir particuler aşamasında gerçekleşen bir eylemin nasıl belirtileceğini gösterir; bağlantı adımı başlamadan önce; oluşturma bittikten sonra.|
|[Nasıl yapılır: MSBuild projelerine özel derleme adımı ekleme](how-to-add-a-custom-build-step-to-msbuild-projects.md)|Derleme dizisine Kullanıcı tanımlı bir aşamanın nasıl ekleneceğini gösterir.|
|[Nasıl yapılır: MSBuild projelerine özel derleme araçları ekleme](how-to-add-custom-build-tools-to-msbuild-projects.md)|Bir yapı aracının belirli bir dosyayla nasıl ilişkilendirileceğini gösterir.|
|[Nasıl yapılır: özel araçları proje özellikleriyle tümleştirme](how-to-integrate-custom-tools-into-the-project-properties.md)|Proje özelliklerine özel bir araç için seçeneklerin nasıl ekleneceğini gösterir.|
|[Nasıl yapılır: hedef Framework ve platform araç takımını değiştirme](how-to-modify-the-target-framework-and-platform-toolset.md)|Birden çok çerçeve veya araç kümesi için bir projenin nasıl derlendiğini gösterir.|

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırından MSVC araç takımını kullanma](building-on-the-command-line.md)
