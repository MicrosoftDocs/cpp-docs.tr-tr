---
title: -DEBUG (hata ayıklama bilgileri üret) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateDebugInformation
- /debug
dev_langs:
- C++
helpviewer_keywords:
- DEBUG linker option
- /DEBUG linker option
- -DEBUG linker option
- PDB files
- debugging [C++], debug information files
- generate debug info linker option
- pdb files, generating debug info
- .pdb files, generating debug info
- debugging [C++], linker option
- program databases [C++]
ms.assetid: 1af389ae-3f8b-4d76-a087-1cdf861e9103
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11b3799447e160a56d73441b60215f1dfcb3e227
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2018
ms.locfileid: "43132141"
---
# <a name="debug-generate-debug-info"></a>/DEBUG (Hata Ayıklama Bilgileri Üret)
```  
/DEBUG[:{FASTLINK|FULL|NONE}]  
```  
  
## <a name="remarks"></a>Açıklamalar  

**/DEBUG** seçeneği, yürütülebilir dosya için hata ayıklama bilgileri oluşturur.    
  
Bağlayıcı hata ayıklama bilgileri bir program veritabanı (PDB) dosyasına yerleştirir. Bu programın ardışık derlemeler sırasında PDB güncelleştirir.  
  
Hata ayıklama için oluşturulan yürütülebilir (.exe dosyası veya DLL) karşılık gelen PDB yolunu ve adını içerir. Hata ayıklayıcı, katıştırılmış adını okur ve programın hata ayıklama PDB kullanır. Bağlayıcı program veritabanı adı için temel programının adını ve .pdb uzantısına kullanır ve yolun oluşturulduğu yere katıştırır. Bu varsayılanı geçersiz kılmak üzere ayarla [/pdb](../../build/reference/pdb-use-program-database.md) ve farklı bir dosya adı belirtin.  

**/Debug: fastlink** seçenektir ve sonrasında Visual Studio 2017'de kullanılabilir. Bu seçenek, yürütülebilir dosyayı oluşturmak için kullanılan tek bir derleme ürünleri özel sembol bilgilerini bırakır. Bu, hata ayıklama bilgilerini nesne dosyaları ve yürütülebilir dosyanın tam kopya oluşturmak yerine oluşturmak için kullanılan kitaplıklar içine dizinler sınırlı bir PDB oluşturur. Bu seçenek, dört kez tam PDB oluşturma Hızlı için ikisinden bağlayabilirsiniz ve yerel olarak hata ayıklama ve derleme ürünleri olması önerilir. Bu sınırlı PDB gerekli derleme ürünleri yürütülebilir dosyayı başka bir bilgisayara dağıtıldığında gibi mevcut olmadığı durumlarda hata ayıklama için kullanılamaz. Bir geliştirici Komut İstemi'nde bu sınırlı PDB'den tam PDB oluşturulacak mspdbcmf.exe Aracı'nı kullanabilirsiniz. Visual Studio'da proje veya çözüm için tam PDB oluşturmak için tam bir PDB dosyası oluşturmak için proje veya derleme menü öğelerini kullanın.  
  
**/Debug: Full** seçeneği tüm özel sembol bilgilerini tek bir derleme ürünleri (nesne dosyaları ve kitaplıkları) tek bir PDB taşır ve bağlantıyı en uzun süren bir parçası olabilir. Ancak, tam PDB, diğer bir yapı ürünleri kullanılamadığında yürütülebilir dağıtıldığında gibi yürütülebilir dosyada hata ayıklamak için kullanılabilir.  
  
**/DEBUG: hiçbiri** seçeneği bir PDB oluşturmaz.  
  
Belirttiğinizde **/DEBUG** ile ek seçenekler, bağlayıcı varsayılan olarak **/Debug: Full** komut satırı ve derleme görevleri dosyası derlemeler için sürüm için yapılar Visual Studio IDE ve hem hata ayıklama ve yayın Visual Studio 2015 veya önceki sürümlerinde oluşturur. Visual Studio 2017'de başlayarak, derleme sistemi IDE içindeki varsayılan olarak **/Debug: fastlink** belirttiğinizde **/DEBUG** hata ayıklama yapıları için seçenek. Diğer Varsayılanları, geriye dönük uyumluluğu korumak için aynıdır.  
  
Derleyicinin [C7 uyumlu](../../build/reference/z7-zi-zi-debug-information-format.md) (/ Z7) seçeneği hata ayıklama bilgileri .obj dosyalarında bırakmak derleyicinin neden olur. Ayrıca [Program veritabanı](../../build/reference/z7-zi-zi-debug-information-format.md) (/zı) derleyici seçeneği hata ayıklama bilgileri .obj dosyası için bir PDB depolamak için. Bağlayıcı için nesnenin PDB önce .obj dosyasında yazılan mutlak yolunda arar ve ardından .obj dosyasına içeren dizin. Bir nesnenin PDB dosya adı veya konumu bağlayıcıya belirtemezsiniz.  
  
[/ INCREMENTAL ](../../build/reference/incremental-link-incrementally.md) /Debug belirlendiğinde kapsanır.  
  
/ DEBUG için varsayılanları değiştirir [/OPT](../../build/reference/opt-optimizations.md) seçeneğinden REF NOREF ve ICF için NOICF, böylece özgün Varsayılanları istiyorsanız açıkça/OPT: ref veya/OPT: ICF belirtmeniz gerekir.  
  
Bir .exe veya .dll hata ayıklama bilgilerini içeren oluşturmak mümkün değildir. Hata ayıklama bilgileri .obj veya .pdb dosyasında her zaman yerleştirilir.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklayın **bağlayıcı** klasör.  
  
3.  Tıklayın **hata ayıklama** özellik sayfası.  
  
4.  Değiştirme **hata ayıklama bilgisi Oluştur** özelliği PDB oluşturmayı etkinleştirin. Bu, Visual Studio 2017'de varsayılan olarak/Debug: fastlink sağlar.  
  
4.  Değiştirme **tam Program veritabanı dosyası oluştur** artımlı her derleme için tam PDB oluşturma/Debug: Full etkinleştirmek için özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
