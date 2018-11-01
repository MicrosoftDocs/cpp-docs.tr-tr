---
title: Kitaplığı Yönetme
ms.date: 11/04/2016
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
ms.openlocfilehash: 69cd03e029d014b9b74a8688f155dfb1f023b55c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477070"
---
# <a name="managing-a-library"></a>Kitaplığı Yönetme

LIB için varsayılan modu, yapı veya bir kitaplık COFF nesnelerin değiştirme sağlamaktır. LIB (nesne dosya kopyalamak için) / Extract veya (içeri aktarma kitaplığı oluşturmak için) / def belirtmeyin bu modda çalışır.

Nesneler ve/veya kitaplıklarla kitaplığından oluşturmak için aşağıdaki sözdizimini kullanın:

```
LIB [options...] files...
```

Bu komut, bir veya daha fazla girişten bir kitaplığı oluşturur *dosyaları*. *Dosyaları* COFF nesnesi dosyalar, 32-bit OMF nesne dosyaları veya mevcut COFF kitaplıklarını olabilir. LIB, belirtilen dosyalardaki tüm nesneleri içeren bir kitaplık oluşturur. Giriş dosyası bir 32-bit OMF nesne dosyası ise, LIB COFF kitaplığı oluşturulmadan önce dönüştürür. LIB, LIB 16-bit sürümü tarafından oluşturulmuş bir kitaplıkta bir 32-bit OMF nesne kabul edemez. Nesne ayıklamak için ilk 16-bit LIB kullanmanız gerekir; Ardından, 32-bit LIB giriş olarak ayıklanan nesne dosyası kullanabilirsiniz.

Varsayılan olarak, LIB temel ilk nesneye veya kitaplık dosyasının adını ve uzantısını kullanarak çıkış dosyasını adlandırır. LIB. Çıktı dosyasını geçerli dizinde konur. Aynı ada sahip bir dosya zaten varsa, çıkış dosyasını varolan dosyanın yerini alır. Var olan bir kitaplık korumak için çıktı dosyası için bir ad belirtmek için/out seçeneği kullanın.

Aşağıdaki seçenekler, oluşturmak ve bir kitaplık değiştirmek için geçerlidir:

**/ LIBPATH:** *dizini*<br/>
Kullanıcının ortam kitaplık yolunu geçersiz kılar. Ayrıntılar için bağlantı açıklamasına bakın [/Libpath](../../build/reference/libpath-additional-libpath.md) seçeneği.

**/ LİSTELEME**<br/>
Standart çıktıya çıkış Kitaplığı hakkında bilgileri görüntüler. Çıktıyı bir dosyaya yönlendirilebilir. / List, varolan kitaplığın içeriğini değiştirmeden belirlemek için kullanabilirsiniz.

**/ NAME:** *dosya adı*<br/>
İçeri aktarma kitaplığı derlerken, içeri aktarma kitaplığını oluşturulmakta olan DLL'in adını belirtir.

**/ NODEFAULTLIB**<br/>
Bir veya daha fazla varsayılan kitaplığı dış başvuruların çözümlenmesi sırasında aradığı kitaplık listesinden kaldırır. Bkz: [/nodefaultlıb](../../build/reference/nodefaultlib-ignore-libraries.md) daha fazla bilgi için.

**/ OUT:** *dosya adı*<br/>
Varsayılan çıktı dosyası adını geçersiz kılar. Varsayılan olarak, çıkış kitaplığı ile komut satırını ve uzantıyı ilk kitaplığı veya nesne dosyasının temel adı geçerli bir dizin oluşturulur. LIB.

**/ REMOVE:** *nesnesi*<br/>
Belirtilen atlar *nesne* çıkış kitaplığı. LIB tüm nesneleri (elinizin altında nesne dosyalarında veya kitaplıklarındaki) birleştirerek ve ardından/Remove ile belirtilen nesneleri silerek bir çıkış kitaplığı oluşturur.

**/ SUBSYSTEM:**{**KONSOL** &AMP;#124; **EFI_APPLICATION** &AMP;#124; **EFI_BOOT_SERVICE_DRIVER** &AMP;#124; **EFI_ROM** &AMP;#124; **EFI_RUNTIME_DRIVER** &AMP;#124; **YEREL** &AMP;#124; **POSIX** &AMP;#124; **WINDOWS** &AMP;#124; **WINDOWSCE**} [, #[. ##]]<br/>
İşletim sistemi, çıkış Kitaplığı'na bağlama tarafından oluşturulan bir programı çalıştırmak üzere anlatır. Daha fazla bilgi için bağlantı açıklamasına bakın [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) seçeneği.

LIB seçenekleri komut satırında belirtilen büyük/küçük harfe duyarlı değildir.

LIB, şu kitaplık yönetim görevlerini gerçekleştirmek için kullanabilirsiniz:

- Nesneleri bir kitaplığa eklemek için varolan kitaplığın dosya adı ve yeni nesneler için dosya adlarını belirtin.

- Kitaplıkları birleştirmek için kitaplık dosya adlarını belirtin. Nesneleri eklemek ve kitaplıkları LIB tek bir komutla birleştirin.

- Kitaplık üyesini yeni bir nesne ile değiştirmek için değiştirilecek üye nesnesi içeren kitaplığın ve yeni bir nesne (veya onu içeren kitaplık) için dosya adını belirtin. Aynı ada sahip bir nesne içinde birden fazla giriş dosyası mevcut olduğunda LIB çıktı kitaplığa LIB komutunda belirtilen son nesne geçirir. Kitaplık üyesini değiştirdiğinizde, yeni nesne veya kitaplık eski nesnesini içeren kitaplık sonra belirtmeyi unutmayın.

- Bir Kitaplığı'ndan bir üyeyi silmek için/remove seçeneğini kullanın. LIB/Remove: komut satırı sipariş bağımsız olarak tüm giriş nesnelerini birleştirme sonra tüm belirtimlerini işler.

> [!NOTE]
>  Bir üyeyi sil olamaz hem bir dosyaya aynı adımda ayıklayın. Önce/extract kullanarak üye nesnesi ayıklamak ardından/Remove'ı yeniden kullanmaya LIB çalıştırma gerekir. Bu davranış, diğer Microsoft ürünlerinde sağlanan 16-bit LIB (için OMF kitaplıkları) farklıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[LIB Başvurusu](../../build/reference/lib-reference.md)