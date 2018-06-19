---
title: Kitaplığı yönetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLibrarianTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLibrarianTool.AdditionalDependencies
- VC.Project.VCLibrarianTool.RemoveObjects
- VC.Project.VCLibrarianTool.LibraryPaths
- VC.Project.VCLibrarianTool.OutputFile
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryNames
- VC.Project.VCLibrarianTool.AdditionalLibraryDirectories
- VC.Project.VCLibrarianTool.ListContentsFile
- VC.Project.VCLibrarianTool.ListContents
- VC.Project.VCLibrarianTool.SubSystemVersion
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryName
- VC.Project.VCLibrarianTool.SubSystem
dev_langs:
- C++
helpviewer_keywords:
- /LIBPATH library manager option
- OUT library manager option
- CONVERT library manager option
- LIBPATH library manager option
- /LIST library manager option
- object files, building and modifying
- -LINK50COMPAT library manager option
- REMOVE library manager option
- SUBSYSTEM library manager option
- /LINK50COMPAT library manager option
- /OUT library manager option
- LIB [C++], managing COFF libraries
- -CONVERT library manager option
- LINK50COMPAT library manager option
- -OUT library manager option
- -REMOVE library manager option
- -LIST library manager option
- /SUBSYSTEM library manager option
- -SUBSYSTEM library manager option
- /REMOVE library manager option
- -LIBPATH library manager option
- object files
- LIST library manager option
- /CONVERT library manager option
ms.assetid: f56a8b85-fbdc-4c09-8d8e-00f0ffe1da53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97c6da9e12e9071b4792476d2e49739a55d7ea8e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379646"
---
# <a name="managing-a-library"></a>Kitaplığı Yönetme
Varsayılan LIB için derleme veya bir kitaplık COFF nesnelerin değiştirmek için moddur. / Extract (bir nesne bir dosyaya kopyalamak için) veya (içeri aktarma kitaplığı oluşturmak için) / def belirtmediğinde LIB bu modda çalışır.  
  
 Nesneleri ve/veya kitaplıkları kitaplığından oluşturmak için aşağıdaki sözdizimini kullanın:  
  
```  
LIB [options...] files...  
```  
  
 Bu komut, bir veya daha fazla girişten kitaplık oluşturur *dosyaları*. *Dosyaları* COFF nesne dosyaları, 32-bit OMF nesne dosyaları veya varolan COFF kitaplıklarını olabilir. LIB belirtilen dosyalarındaki tüm nesneleri içeren bir kitaplık oluşturur. 32-bit OMF nesne dosyasına bir giriş dosyası olup olmadığını LIB COFF'ye kitaplığı oluşturulmadan önce dönüştürür. LIB LIB 16-bit sürümü ile oluşturulmuş bir Kitaplığı'nda bir 32 bit OMF nesne kabul edemez. Nesne ayıklamak için ilk 16 bit LIB kullanmanız gerekir; Ardından, 32-bit LIB giriş olarak ayıklanan nesne dosyası kullanabilirsiniz.  
  
 Varsayılan olarak, LIB temel ilk nesne veya kitaplık dosyasının adını ve uzantısını kullanarak çıktı dosyası adları. lib. Çıktı dosyası geçerli dizinde yerleştirilir. Aynı ada sahip bir dosya zaten varsa, çıktı dosyasını varolan dosyanın yerini alır. Var olan bir kitaplık korumak için çıktı dosyası için bir ad belirtmek için /OUT seçeneğini kullanın.  
  
 Aşağıdaki seçenekler, derleme ve bir kitaplık değiştirme için geçerlidir:  
  
 / LIBPATH: `dir`  
 Ortam Kitaplığı yol geçersiz kılar. BAĞLANTI açıklaması Ayrıntılar için bkz [/Libpath](../../build/reference/libpath-additional-libpath.md) seçeneği.  
  
 / LİSTESİ  
 Standart çıktı çıkış kitaplığına hakkında bilgileri görüntüler. Çıktıyı bir dosyaya yönlendirilebilir. / List değiştirmeden var olan bir kitaplık içeriğini belirlemek için kullanabilirsiniz.  
  
 / NAME: *dosya adı*  
 İçeri aktarma kitaplığı oluştururken, içeri aktarma kitaplığını oluşturulmakta olan DLL adını belirtir.  
  
 / NODEFAULTLIB  
 Bir veya daha fazla varsayılan kitaplık dış başvuruları çözülürken arar kitaplıkları listesinden kaldırır. Bkz: [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) daha fazla bilgi için.  
  
 / ÇIKIŞI: *dosya adı*  
 Varsayılan çıkış filename geçersiz kılar. Varsayılan olarak, çıktı kitaplığı temel dosyasının adı ilk kitaplığı veya nesne komut satırı ve uzantısı ile geçerli dizinde oluşturulur. lib.  
  
 / Kaldır: *nesnesi*  
 Belirtilen atlar *nesne* çıkış kitaplığından. LIB çıktı kitaplığı tüm nesneler (nesne dosya ya da kitaplıkları kullanılıp) birleştirerek ve ardından/Remove ile belirtilen tüm nesneleri silme oluşturur.  
  
 / SUBSYSTEM: {KONSOL &AMP;#124; EFI_APPLICATION &AMP;#124; EFI_BOOT_SERVICE_DRIVER &AMP;#124; EFI_ROM &AMP;#124; EFI_RUNTIME_DRIVER &AMP;#124; YEREL &AMP;#124; POSIX &AMP;#124; WINDOWS &AMP;#124; WINDOWSCE} [, #[. ##]]  
 İşletim sistemi, çıkış kitaplığına bağlama tarafından oluşturulan bir programı çalıştırmak anlatır. BAĞLANTI açıklaması daha fazla bilgi için bkz [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) seçeneği.  
  
 Komut satırında belirtilen LIB seçenekleri büyük küçük harfe duyarlı değildir.  
  
 LIB aşağıdaki kitaplığı yönetim görevlerini gerçekleştirmek için kullanabilirsiniz:  
  
-   Bir kitaplık nesneleri eklemek için varolan kitaplık için dosya adı ve dosya adları yeni nesneler için belirtin.  
  
-   Kitaplıkları birleştirmek için kitaplık dosya adlarını belirtin. Nesne eklemek ve kitaplıkları tek bir LIB komutu ile birleştirin.  
  
-   Kitaplık üyesini ile yeni bir nesne değiştirmek için değiştirilecek üye nesnesini içeren kitaplığı ve yeni bir nesne (veya onu içeren kitaplık) için dosya adı belirtin. Aynı ada sahip bir nesne birden fazla girdi dosyasında mevcut olduğunda LIB çıktı kitaplığa LIB komutunda belirtilen son nesne koyar. Kitaplık üyesini değiştirdiğinizde, yeni nesne veya kitaplık eski nesnesini içeren kitaplığı sonra belirttiğinizden emin olun.  
  
-   Bir Kitaplığı'ndan bir üyeyi silmek için/remove seçeneğini kullanın. LIB komut satırı sipariş bağımsız olarak tüm giriş nesneleri birleştirme sonra/Remove herhangi belirtimlerini işler.  
  
> [!NOTE]
>  Bir üyeyi silmek hem aynı adımını dosyasında ayıklamak olamaz. Gerekir ilk/extract kullanarak üye nesnesi ayıklayın ve ardından LIB/Remove kullanarak yeniden çalıştırın. Bu davranış, diğer Microsoft ürünleri sağlanan 16 bit LIB (için OMF kitaplıkları) farklıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LIB Başvurusu](../../build/reference/lib-reference.md)