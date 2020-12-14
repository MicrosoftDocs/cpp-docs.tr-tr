---
description: Daha fazla bilgi edinin:/DEBUG (hata ayıklama bilgileri üret)
title: /DEBUG (Hata Ayıklama Bilgileri Üret)
ms.date: 05/16/2019
f1_keywords:
- VC.Project.VCLinkerTool.GenerateDebugInformation
- /debug
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
ms.openlocfilehash: b0ef30fe7cb5eb5af0c46d6f6a8f3533d2e7d6ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201826"
---
# <a name="debug-generate-debug-info"></a>/DEBUG (Hata Ayıklama Bilgileri Üret)

```
/DEBUG[:{FASTLINK|FULL|NONE}]
```

## <a name="remarks"></a>Açıklamalar

**/Debug** seçeneği yürütülebilir dosya için hata ayıklama bilgileri oluşturur.

Bağlayıcı, hata ayıklama bilgilerini bir program veritabanı (PDB) dosyasına koyar. Programın sonraki derlemeleri için PDB 'yi güncelleştirir.

Hata ayıklama için oluşturulan yürütülebilir (. exe dosyası veya DLL), karşılık gelen PDB 'nin adını ve yolunu içerir. Hata ayıklayıcı gömülü adı okur ve programda hata ayıklarken PDB 'yi kullanır. Bağlayıcı program veritabanını adlandırmak için programın temel adını ve. pdb uzantısını kullanır ve yolu oluşturulduğu yere katıştırır. Bu varsayılanı geçersiz kılmak için, [/pdb](pdb-use-program-database.md) ayarlayın ve farklı bir dosya adı belirtin.

**/Debug: FASTLINK** seçeneği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir. Bu seçenek, yürütülebilir dosyayı oluşturmak için kullanılan ayrı derleme ürünlerinde özel sembol bilgilerini bırakır. Tam kopya yapmak yerine yürütülebilir dosyayı oluşturmak için kullanılan nesne dosyalarındaki ve kitaplıklardaki hata ayıklama bilgilerinde dizinleyen sınırlı bir PDB oluşturur. Bu seçenek, iki ile dört kat arasında tam PDB oluşturma kadar hızlı bağlantı oluşturabilir ve yerel olarak hata ayıklarken ve derleme ürünlerini kullanılabilir hale getirebilmeniz durumunda önerilir. Bu sınırlı PDB, gerekli derleme ürünleri kullanılabilir olmadığında (örneğin, yürütülebilir dosya başka bir bilgisayara dağıtıldığında) hata ayıklama için kullanılamaz. Bir geliştirici komut isteminde, bu sınırlı PDB 'den tam PDB oluşturmak için mspdbcmf.exe aracını kullanabilirsiniz. Visual Studio 'da, proje veya çözüm için tam PDB oluşturmak üzere tam bir PDB dosyası oluşturmak için proje veya derleme menü öğelerini kullanın.

**/Debug: Full** seçeneği, bireysel derleme ürünlerinden (nesne dosyaları ve kitaplıklar) bulunan tüm özel sembol bilgilerini tek bir PDB 'ye taşıdır ve bağlantının en uzun zaman alan parçası olabilir. Ancak, tam PDB, yürütülebilir dosya dağıtıldığında olduğu gibi başka bir derleme ürünü olmadığında yürütülebilir dosyada hata ayıklamak için kullanılabilir.

**/Debug: None** seçeneği pdb oluşturmaz.

Ek seçenek olmadan **/Debug** belirttiğinizde, bağlayıcı komut satırı ve derleme görevleri dosyası yapıları için varsayılan olarak **/Debug: Full** , Visual Studio IDE 'deki yayın yapıları için ve Visual Studio 2015 ve önceki sürümlerde hem hata ayıklama hem de yayın yapıları için. Visual Studio 2017 ' den başlayarak, hata ayıklama yapıları için **/Debug** SEÇENEĞINI belirttiğinizde IDE 'deki derleme sistemi varsayılan olarak **/Debug: fastlink** olarak belirlenmiştir. Geriye dönük uyumluluk sağlamak için diğer varsayılanlar değiştirilmez.

Derleyicinin [C7 uyumlu](z7-zi-zi-debug-information-format.md) (/Z7) seçeneği derleyicinin hata ayıklama bilgilerini. obj dosyalarında bırakmasını sağlar. Ayrıca, hata ayıklama bilgilerini. obj dosyası için bir PDB 'de depolamak için [Program veritabanı](z7-zi-zi-debug-information-format.md) (/Zi) derleyici seçeneğini de kullanabilirsiniz. Bağlayıcı, önce. obj dosyasında yazılmış mutlak yoldaki nesnenin PDB 'sini, sonra. obj dosyasını içeren dizinde arar. Bir nesnenin PDB dosya adını veya konumunu bağlayıcıya belirtemezsiniz.

[/Incre/Debug](incremental-link-incrementally.md) belirtildiğinde uygulanır.

/DEBUG [/opt](opt-optimizations.md) seçeneğinin varsayılan değerlerini ref 'den NOREF 'e ve ICF 'den NOICF 'ye değiştirir, bu nedenle özgün Varsayılanları istiyorsanız, açıkça/OPT: ref veya/OPT: ICF belirtmeniz gerekir.

Hata ayıklama bilgilerini içeren bir. exe veya. dll oluşturulamaz. Hata ayıklama bilgileri her zaman bir. obj veya. pdb dosyasına yerleştirilir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Hata ayıklama** Özellik sayfasına tıklayın.

1. PDB oluşturmayı etkinleştirmek için **hata ayıklama bilgisi oluştur** özelliğini değiştirin. Bu,/DEBUG: FASTLINK ' i Visual Studio 2017 ve üzeri sürümlerde varsayılan olarak sunar.

1. Tüm artımlı derlemede tam PDB oluşturma için/DEBUG: FULL öğesini etkinleştirmek üzere **tam program veritabanı dosyası oluştur** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
