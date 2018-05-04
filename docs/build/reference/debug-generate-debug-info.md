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
ms.openlocfilehash: f93c47a0f96cf0b75b453bcea97212d4ab2fd6d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="debug-generate-debug-info"></a>/DEBUG (Hata Ayıklama Bilgileri Üret)
```  
/DEBUG[:{FASTLINK|FULL|NONE}]  
```  
  
## <a name="remarks"></a>Açıklamalar  

**/DEBUG** seçeneği yürütülebilir dosyası için hata ayıklama bilgisi oluşturur.    
  
Bağlayıcı hata ayıklama bilgileri bir program veritabanı (PDB) dosyasına yerleştirir. Bu program sonraki derlemeleri sırasında PDB güncelleştirir.  
  
Hata ayıklama için oluşturulan bir yürütülebilir dosya (.exe dosyası ya da DLL) adını ve karşılık gelen PDB yolunu içerir. Hata ayıklayıcı katıştırılmış adını okur ve program hata ayıklarken PDB kullanır. Bağlayıcı program veritabanı adı için temel programının adını ve uzantısını .pdb kullanır ve oluşturulduğu yolu katıştırır. Bu varsayılanı geçersiz kılmak için ayarlanmış [/pdb](../../build/reference/pdb-use-program-database.md) ve farklı bir dosya adı belirtin.  

**/DEBUG:FASTLINK** seçeneği yürütülebilir dosyayı oluşturmak için kullanılan tek tek derleme ürünlerinde özel simge bilgilerini bırakır. Hata ayıklama bilgilerini nesne dosyaları ve kitaplıkları tam bir kopya yapmak yerine yürütülebilir dosyayı oluşturmak için kullanılan içine dizinler sınırlı bir PDB oluşturur. Bu seçenek, iki dört kez tam PDB nesil olarak hızlı şekilde bağlayabilirsiniz ve yerel olarak hata ayıklama ve yapı ürünleri olması önerilir. Bu sınırlı PDB gerekli derleme ürünleri yürütülebilir dosyayı başka bir bilgisayara dağıtıldığında gibi kullanılabilir olmadığında hata ayıklama için kullanılamaz. Bir geliştirici komut istemi tam PDB sınırlı bu PDB oluşturmak için mspdbcmf.exe aracını kullanabilirsiniz. Visual Studio Proje ve çözüm için tüm PDB oluşturmak için tam PDB dosyası oluşturmak için proje veya yapı menü öğeleri kullanın.  
  
**/DEBUG:FULL** seçeneği tüm özel sembol bilgileri tek tek derleme ürünler (nesne dosyaları ve kitaplıkları) tek bir PDB taşır ve bağlantıyı en uzun süren bir parçası olabilir. Ancak, tam PDB başka bir yapı ürünleri kullanılamadığında yürütülebilir dağıtıldığında gibi yürütülebilir hata ayıklamak için kullanılabilir.  
  
**/DEBUG: hiçbiri** seçeneği bir PDB oluşturmaz.  
  
Belirttiğinizde **/DEBUG** bağlayıcı hiçbir ek seçenekleri, varsayılan olarak **/DEBUG:FULL** komut satırı ve derleme görevleri dosyası derlemeler için sürüm için derlemeler Visual Studio IDE ve hata ayıklama ve sürüm Visual Studio 2015 ve önceki sürümlerinde oluşturur. İçinde Visual Studio 2017'den itibaren IDE'de yapı sistem varsayılan olarak **/DEBUG:FASTLINK** belirttiğinizde **/DEBUG** hata ayıklama derlemeleri için seçenek. Diğer Varsayılanları, geriye dönük uyumluluğu korumak için aynıdır.  
  
Derleyicinin [C7 uyumlu](../../build/reference/z7-zi-zi-debug-information-format.md) (/ Z7) seçeneği .obj dosyaları hata ayıklama bilgileri bırakmayı derleyicinin neden olur. Aynı zamanda [Program veritabanı](../../build/reference/z7-zi-zi-debug-information-format.md) PDB .obj dosyası için hata ayıklama bilgilerini depolamak için derleyici seçeneği (/ Zi). Bağlayıcı için nesnenin PDB ilk .obj dosyasında yazılan mutlak yolunda arar ve ardından .obj dosyayı içeren dizinde. Bir nesnenin PDB dosya adı veya bağlayıcı konumunu belirtemezsiniz.  
  
[/ INCREMENTAL ](../../build/reference/incremental-link-incrementally.md) /Debug belirtildiğinde kapsanır.  
  
/ DEBUG için varsayılanları değiştirir [/OPT](../../build/reference/opt-optimizations.md) seçeneğinden REF NOREF gelen ve giden ICF NOICF için şekilde özgün Varsayılanları istiyorsanız, açıkça /OPT:REF veya /OPT:ICF belirtmeniz gerekir.  
  
Bir .exe veya hata ayıklama bilgilerini içeren .dll oluşturmak mümkün değil. Hata ayıklama bilgileri her zaman bir .obj veya .pdb dosyasında yerleştirilir.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **hata ayıklama** özellik sayfası.  
  
4.  Değiştirme **hata ayıklama bilgisi üret** özelliği PDB oluşturmayı etkinleştirin. Bu, varsayılan olarak Visual Studio 2017 /DEBUG:FASTLINK sağlar.  
  
4.  Değiştirme **oluşturmak tam Program veritabanı dosya** /DEBUG:FULL her Artımlı derleme için tam PDB oluşturmayı etkinleştirmek için özellik.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
