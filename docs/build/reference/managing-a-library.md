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
ms.openlocfilehash: de55059834a0887d487b7be38377af9984512b75
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336403"
---
# <a name="managing-a-library"></a>Kitaplığı Yönetme

LIB için varsayılan mod, COFF nesnelerinin kitaplığını oluşturmak veya değiştirmektir. /EXTRACT (bir nesneyi bir dosyaya kopyalamak için) veya /DEF (alma kitaplığı oluşturmak için) belirtmediğinizde LIB bu modda çalışır.

Nesnelerden ve/veya kitaplıklardan kitaplık oluşturmak için aşağıdaki sözdizimini kullanın:

```
LIB [options...] files...
```

Bu komut, bir veya daha fazla giriş *dosyasından*kitaplık oluşturur. *Dosyalar* COFF nesne dosyaları, 32-bit OMF nesne dosyaları veya varolan COFF kitaplıkları olabilir. LIB, belirtilen dosyalardaki tüm nesneleri içeren bir kitaplık oluşturur. Giriş dosyası 32 bit OMF nesne dosyasıysa, LIB kitaplığı oluşturmadan önce dosyayı COFF'a dönüştürür. LIB, LIB'in 16 bit sürümü tarafından oluşturulan bir kitaplıkta bulunan 32 bit omf nesnesini kabul edemez. Nesneyi ayıklamak için önce 16 bit LIB kullanmanız gerekir; sonra çıkarılan nesne dosyasını 32-bit LIB'e giriş olarak kullanabilirsiniz.

Varsayılan olarak, LIB ilk nesne veya kitaplık dosyasının temel adını ve uzantısı .lib kullanarak çıktı dosyasını adlandırır. Çıktı dosyası geçerli dizine konur. Bir dosya zaten aynı ada sahipse, çıktı dosyası varolan dosyanın yerini alır. Varolan bir kitaplığı korumak için, çıktı dosyası için bir ad belirtmek için /OUT seçeneğini kullanın.

Aşağıdaki seçenekler kitaplık oluşturma ve değiştirme için geçerlidir:

**/LIBPATH:** *dir*<br/>
Çevre kitaplığı yolunu geçersiz kılar. Ayrıntılar için LINK [/LIBPATH](libpath-additional-libpath.md) seçeneğinin açıklamasına bakın.

**/Lİste**<br/>
Çıktı kitaplığı hakkındaki bilgileri standart çıktıya görüntüler. Çıktı bir dosyaya yönlendirilebilir. Varolan bir kitaplığın içeriğini değiştirmeden belirlemek için /LIST'i kullanabilirsiniz.

**/NAME:** *dosya adı*<br/>
Bir alma kitaplığı oluştururken, içe aktarma kitaplığı için inşa edilmekte olan DLL'nin adını belirtir.

**/NODEFAULTLIB**<br/>
Dış başvuruları çözerken aradığı kitaplıklar listesinden bir veya daha fazla varsayılan kitaplık kaldırır. Daha fazla bilgi için [/NODEFAULTLIB'e](nodefaultlib-ignore-libraries.md) bakın.

**/OUT:** *dosya adı*<br/>
Varsayılan çıktı dosya adını geçersiz kılar. Varsayılan olarak, çıktı kitaplığı, komut satırında ilk kitaplığın veya nesne dosyasının temel adı ve uzantı .lib ile geçerli dizinde oluşturulur.

**/REMOVE:** *nesne*<br/>
Belirtilen *nesneyi* çıkış kitaplığından atlar. LIB, tüm nesneleri (nesne dosyalarında veya kitaplıklarda) birleştirerek ve sonra /REMOVE ile belirtilen nesneleri silerek bir çıktı kitaplığı oluşturur.

**/ALT SİsteM:**{**KONSOL** &#124; **EFI_APPLICATION** &#124; **EFI_BOOT_SERVICE_DRIVER &#124;** &#124; **EFI_ROM** &#124; **EFI_RUNTIME_DRIVER &#124;** &#124; **YEREL** &#124; **POSIX** &#124; **WINDOWSCE** &#124; **WINDOWSCE**}[,####]]<br/>
İşletim sistemine çıktı kitaplığına bağlanarak oluşturulan bir programın nasıl çalıştırılabildiğini söyler. Daha fazla bilgi için LINK [/SUBSYSTEM](subsystem-specify-subsystem.md) seçeneğinin açıklamasına bakın.

Komut satırında belirtilen LIB seçenekleri büyük/küçük harf duyarlı değildir.

Aşağıdaki kitaplık yönetimi görevlerini gerçekleştirmek için LIB'i kullanabilirsiniz:

- Kitaplıklara nesneler eklemek için, varolan kitaplığın dosya adını ve yeni nesnelerin dosya adlarını belirtin.

- Kitaplıkları birleştirmek için kitaplık dosya adlarını belirtin. Nesneler ekleyebilir ve kitaplıkları tek bir LIB komutuyla birleştirebilirsiniz.

- Kitaplık üyesini yeni bir nesneyle değiştirmek için, değiştirilecek üye nesneyi içeren kitaplığı ve yeni nesnenin (veya onu içeren kitaplığın) dosya adını belirtin. Aynı ada sahip bir nesne birden fazla giriş dosyasında varsa, LIB, LIB komutunda belirtilen son nesneyi çıkış kitaplığına koyar. Bir kitaplık üyesini değiştirdiğinizde, eski nesneyi içeren kitaplıktan sonra yeni nesneyi veya kitaplığı belirttiğinden emin olun.

- Bir üyeyi kitaplıktan silmek için /REMOVE seçeneğini kullanın. LIB, komut satırı sırası ne olursa olsun tüm giriş nesnelerini birleştirdikten sonra /REMOVE'un tüm belirtimlerini işler.

> [!NOTE]
> Hem üyeyi siler hem de aynı adımda bir dosyaya ayıklayamazsınız. Önce /EXTRACT kullanarak üye nesneyi ayıklamanız, sonra /REMOVE kullanarak LIB'i yeniden çalıştırmanız gerekir. Bu davranış, diğer Microsoft ürünlerinde sağlanan 16 bit LIB'den (OMF kitaplıkları için) farklıdır.

## <a name="see-also"></a>Ayrıca bkz.

[LIB Referans](lib-reference.md)
