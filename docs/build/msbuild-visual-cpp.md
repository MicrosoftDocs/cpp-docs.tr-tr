---
title: MSBuild komut satırında - C++
ms.date: 12/12/2018
helpviewer_keywords:
- MSBuild
ms.assetid: 7a1be7ff-0312-4669-adf2-5f5bf507d560
ms.openlocfilehash: e95d99cf5c63c824bb9bade8e76bc3ca99079669
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220570"
---
# <a name="msbuild-on-the-command-line---c"></a>MSBuild komut satırında - C++

Genel olarak, proje özelliklerini ayarlama ve MSBuild sistemi çağırmak için Visual Studio kullanmanızı öneririz. Ancak, kullanabileceğiniz **MSBuild** komut isteminden doğrudan aracı. Yapı işlemi oluşturma ve düzenleme bir proje dosyası (.vcxproj) bilgileri tarafından denetlenir. Proje dosyası derleme aşamaları, koşullar ve olayları temel derleme seçenekleri belirtir. Ayrıca, sıfır belirtebilirsiniz veya daha fazla komut satırı *seçenekleri* bağımsız değişkenler.

> **msbuild.exe** [ *project_file* ] [ *options* ]

Kullanım **/target** (veya **/t**) ve **/Property** (veya **/p**) belirli özelliklerine ve olan hedefleri geçersiz kılmak için komut satırı seçenekleri Proje dosyasında belirtilen.

Proje dosyasının asıl işlevi belirtmek için olan bir *hedef*, projenizin ve girişlere ve çıkışlara bu işlemi gerçekleştirmek için gereken uygulanacak belirli bir işlem olduğu. Bir proje dosyası, varsayılan hedefin içerebileceği bir veya daha fazla hedefleri belirtebilirsiniz.

Her hedef bir veya daha fazla bir dizi oluşur *görevleri*. Her görev bir yürütülebilir komut içeren bir .NET Framework sınıfı tarafından temsil edilir. Örneğin, [CL görevi](/visualstudio/msbuild/cl-task) içeren [cl.exe](reference/compiling-a-c-cpp-program.md) komutu.

A *görev parametresi* sınıf görevi özelliğidir ve genellikle yürütülebilir komutun komut satırı seçeneğini temsil eder. Örneğin, `FavorSizeOrSpeed` parametresinin `CL` görev karşılık gelen **/Os** ve **/Ot** derleyici seçenekleri.

Ek görev parametreleri MSBuild altyapısını destekler. Örneğin, `Sources` görev parametresi, diğer görevler tarafından tüketilebilecek bir görevler kümesini belirtir. Msbuil görevleri hakkında daha fazla bilgi için bkz. [görev başvurusu](/visualstudio/msbuild/msbuild-task-reference).

Çoğu görevler, girdileri ve çıktıları, dosya adları, yollar ve dize, sayısal ya da Boole parametreleri gibi gerektirir. Örneğin, ortak bir giriş derlenecek bir .cpp kaynak dosyasının adıdır. Önemli girdi parametresi yapı yapılandırması ve platformu, örneğin, belirten bir dizedir "hata ayıklama\|Win32". Giriş ve çıkışları bir veya daha fazla kullanıcı tarafından tanımlanan XML tarafından belirtilen `Item` içindeki öğe bir `ItemGroup` öğesi.

Kullanıcı tanımlı bir proje dosyası da belirtebilirsiniz *özellikleri* ve `ItemDefinitionGroup` *öğeleri*. Özellikler ve öğeler yapıda değişkenler olarak kullanılabilen ad/değer çiftlerini oluşturur. Bir çiftin ad bileşeni tanımlayan bir *makrosu*, ve değer bileşeni bildirir *makro değerini*. Özellik makrosuna $ kullanılarak erişilen (*adı*) gösterimi yanı sıra, öğe makrosu erişilen kullanarak %(*adı*) gösterimi.

Project dosyasındaki diğer XML öğeleri makroları test ve daha sonra koşullu olarak herhangi bir makronun değerini ayarlayabilir veya yapının yürütülmesini denetleme. Makro adları ve değişmez değer dizeleri, yol ve dosya adı gibi yapılar oluşturmak için birleştirilebilir. Komut satırında **/Property** seçeneği ayarlar ya da proje özelliğini geçersiz kılar. Öğeleri, komut satırında başvurulamaz.

Önce veya sonra başka bir hedef, MSBuild sistemi bir hedefi koşullu olarak yürütebilir. Ayrıca, sistem hedefin kullandığı dosyaların yaydığı dosyalardan daha yeni olup şirket tabanlı bir hedef oluşturabilir.

MSBuild hakkında daha fazla bilgi için bkz:

- [MSBuild](/visualstudio/msbuild/msbuild) genel bakış, MSBuild kavramları.

- [MSBuild başvurusu](/visualstudio/msbuild/msbuild-reference) MSBuild sistemi ilgili başvuru bilgileri.

- [Proje dosyası şema başvurusu](/visualstudio/msbuild/msbuild-project-file-schema-reference) özelliklerini ve üst ve alt öğeleri ile birlikte MSBuild XML şema öğelerini listeler. Özellikle dikkat edin [ItemGroup](/visualstudio/msbuild/itemgroup-element-msbuild), [PropertyGroup](/visualstudio/msbuild/propertygroup-element-msbuild), [hedef](/visualstudio/msbuild/target-element-msbuild), ve [görev](/visualstudio/msbuild/task-element-msbuild) öğeleri.

- [Komut satırı başvurusu](/visualstudio/msbuild/msbuild-command-line-reference) komut satırı bağımsız değişkenlerini ve msbuild.exe ile kullanabileceğiniz seçenekleri açıklar.

- [Görev başvurusu](/visualstudio/msbuild/msbuild-task-reference) açıklar MSBuild görevleri. Özellikle Visual C++'a özel görevlere dikkat edin: [BscMake görevi](/visualstudio/msbuild/bscmake-task), [CL görevi](/visualstudio/msbuild/cl-task), [CPPClean görevi](/visualstudio/msbuild/cppclean-task), [LIB görevi](/visualstudio/msbuild/lib-task), [bağlantı görev](/visualstudio/msbuild/link-task), [MIDL görevi](/visualstudio/msbuild/midl-task), [MT görevi](/visualstudio/msbuild/mt-task), [RC görevi](/visualstudio/msbuild/rc-task), [SetEnv görevi](/visualstudio/msbuild/setenv-task), [VCMessage görevi](/visualstudio/msbuild/vcmessage-task)

## <a name="in-this-section"></a>Bu Bölümde

|Terim|Tanım|
|----------|----------------|
|[İzlenecek yol: C++ Projesi Oluşturmak için MSBuild Kullanma](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)|Visual Studio oluşturma işlemini gösterir C++ kullanarak proje **MSBuild**.|
|[Nasıl yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma](how-to-use-build-events-in-msbuild-projects.md)|Gösterilmektedir yapı particuler aşamasında oluşan bir eylem belirtin: oluşturma başlamadan önce; bağlantı adım başlatılmadan önce; ya da yapı sona erdikten sonra.|
|[Nasıl yapılır: MSBuild Projelerine Özel Derleme Adımı Ekleme](how-to-add-a-custom-build-step-to-msbuild-projects.md)|Kullanıcı tanımlı bir aşama için derleme sıra ekleme gösterir.|
|[Nasıl yapılır: MSBuild Projelerine Özel Derleme Araçları Ekleme](how-to-add-custom-build-tools-to-msbuild-projects.md)|Bir yapı aracı belirli bir dosya ile ilişkilendirmek nasıl gösterir.|
|[Nasıl yapılır: Özel Araçlarla Proje Özelliklerini Tümleştirme](how-to-integrate-custom-tools-into-the-project-properties.md)|Proje özellikleri için özel bir araç seçenekleri gösterilmektedir.|
|[Nasıl yapılır: Hedef Çerçeve ve Platform Araç Kümesini Değiştirme](how-to-modify-the-target-framework-and-platform-toolset.md)|Birden çok çerçeve veya araç takımları için proje derlemek nasıl gösterir.|

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırından MSVC araç takımını kullanma](building-on-the-command-line.md)
