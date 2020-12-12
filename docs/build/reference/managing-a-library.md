---
description: 'Daha fazla bilgi edinin: bir kitaplığı yönetme'
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
ms.openlocfilehash: f862dfd460bb51cdf6e855c87b08b7426a5642d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199135"
---
# <a name="managing-a-library"></a>Kitaplığı Yönetme

LıB için varsayılan mod, COFF nesnelerinin bir kitaplığını derlemek veya değiştirmektir. Bu modda,/EXTRACT (bir nesneyi bir dosyaya kopyalamak için) veya/DEF (içeri aktarma kitaplığı oluşturmak için) belirtmezseniz bu modda çalışır.

Nesnelerden ve/veya kitaplıklarından bir kitaplık oluşturmak için aşağıdaki sözdizimini kullanın:

```
LIB [options...] files...
```

Bu komut bir veya daha *fazla giriş dosyasından* bir kitaplık oluşturur. *Dosyalar* , nesne dosyalarını, 32-BIT OMF nesne dosyalarını veya var olan COFF kitaplıklarını COFF olabilir. LıB belirtilen dosyalardaki tüm nesneleri içeren bir kitaplık oluşturur. Bir giriş dosyası 32-bit OMF nesne dosyası ise, LIB kitaplığı oluşturmadan önce onu COFF 'ye dönüştürür. LıB, LıB 'in 16 bit sürümü tarafından oluşturulmuş bir kitaplıkta olan 32 bitlik bir OMF nesnesini kabul edemez. Nesneyi ayıklamak için öncelikle 16 bit LIB kullanmanız gerekir; ardından, ayıklanan nesne dosyasını 32 bit LIB 'e giriş olarak kullanabilirsiniz.

Varsayılan olarak, LIB ilk nesne veya kitaplık dosyasının temel adını ve. LIB uzantısını kullanarak çıkış dosyasını adlandırır. Çıkış dosyası geçerli dizine konur. Aynı ada sahip bir dosya zaten varsa, çıkış dosyası mevcut dosyanın yerini alır. Var olan bir kitaplığı korumak için, çıkış dosyası için bir ad belirtmek üzere/OUT seçeneğini kullanın.

Aşağıdaki seçenekler bir kitaplığı oluşturmak ve değiştirmek için geçerlidir:

**/Libpath:** *dir*<br/>
Ortam kitaplığı yolunu geçersiz kılar. Ayrıntılar için bağlantı [/LIBPATH](libpath-additional-libpath.md) seçeneğinin açıklamasına bakın.

**/LIST**<br/>
Standart çıktıya çıkış kitaplığıyla ilgili bilgileri görüntüler. Çıktı bir dosyaya yönlendirilebilir. Var olan bir kitaplığın içeriğini değiştirmeden anlamak için/LIST ' i kullanabilirsiniz.

**/Name:** *dosya adı*<br/>
İçeri aktarma kitaplığı oluştururken, içeri aktarma kitaplığının oluşturulduğu DLL 'in adını belirtir.

**/NODEFAULTLıB**<br/>
Dış başvuruları çözümlerken aradığı kitaplık listesinden bir veya daha fazla varsayılan kitaplığı kaldırır. Daha fazla bilgi için bkz. [/nodefaultlib](nodefaultlib-ignore-libraries.md) .

**/Out:** *filename*<br/>
Varsayılan çıkış dosya adını geçersiz kılar. Varsayılan olarak, çıktı kitaplığı geçerli dizinde, komut satırındaki ilk kitaplığın veya nesne dosyasının temel adı ve. lib uzantısı ile oluşturulur.

**/Remove:** *nesne*<br/>
Çıkış kitaplığından belirtilen *nesneyi* atlar. LıB tüm nesneleri birleştirerek (nesne dosyalarında veya kitaplıklarda) ve sonra/REMOVE. ile belirtilen tüm nesneleri silerek bir çıktı kitaplığı oluşturur.

**/Subsystem:**{**CONSOLE** &#124; **EFI_APPLICATION** &#124; **EFI_BOOT_SERVICE_DRIVER** &#124; **EFI_ROM** &#124; **EFI_RUNTIME_DRIVER** &#124; **Yerel** &#124; **POSIX** &#124; **WINDOWS** &#124; **WindowsCE**} [, # [. # #]]<br/>
İşletim sistemine, çıkış kitaplığına bağlanarak oluşturulan bir programın nasıl çalıştırılacağını söyler. Daha fazla bilgi için LINK [/Subsystem](subsystem-specify-subsystem.md) seçeneğinin açıklamasına bakın.

Komut satırında belirtilen LıB seçenekleri büyük/küçük harfe duyarlı değildir.

Aşağıdaki kitaplık yönetim görevlerini gerçekleştirmek için LIB 'i kullanabilirsiniz:

- Bir kitaplığa nesne eklemek için, var olan kitaplığın dosya adını ve yeni nesneler için dosya adlarını belirtin.

- Kitaplıkları birleştirmek için kitaplık dosyası adlarını belirtin. Nesneleri ekleyebilir ve kitaplıkları tek bir LIB komutuyla birleştirebilirsiniz.

- Bir kitaplık üyesini yeni bir nesneyle değiştirmek için, değiştirilecek üye nesnesini içeren kitaplığı ve yeni nesnenin (veya onu içeren kitaplığın) dosya adını belirtin. Birden fazla giriş dosyasında aynı ada sahip bir nesne varsa, LIB LIB komutunda belirtilen son nesneyi çıkış kitaplığına koyar. Bir kitaplık üyesini değiştirdiğinizde, eski nesneyi içeren kitaplıktan sonra yeni nesneyi veya kitaplığı belirttiğinizden emin olun.

- Bir kitaplıktan üye silmek için/REMOVE seçeneğini kullanın. LıB, komut satırı sıralarından bağımsız olarak tüm giriş nesneleri birleştirildikten sonra/REMOVE 'ın tüm belirtimlerini işler.

> [!NOTE]
> Her ikisi de bir üyeyi silemez ve aynı adımda bir dosyaya ayıklayabilir. Önce/EXTRACT kullanarak üye nesnesini ayıklamanız, sonra/REMOVE. kullanarak LIB 'i yeniden çalıştırmanız gerekir. Bu davranış, diğer Microsoft ürünlerinde sağlanmış olan 16 bit LıB 'den (OMF kitaplıkları için) farklıdır.

## <a name="see-also"></a>Ayrıca bkz.

[LıB başvurusu](lib-reference.md)
