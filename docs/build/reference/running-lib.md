---
title: "LIB çalıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLibrarianTool.TargetMachine
- Lib
- VC.Project.VCLibrarianTool.PrintProgress
- VC.Project.VCLibrarianTool.SuppressStartupBanner
dev_langs: C++
helpviewer_keywords:
- -MACHINE target platform option
- command files, LIB
- MACHINE target platform option
- colon command files
- VERBOSE library manager option
- /NOLOGO library manager option
- dash option specifier
- /MACHINE target platform option
- forward slash option specifier
- -NOLOGO library manager option
- LIB [C++], running LIB
- -VERBOSE library manager option
- /VERBOSE library manager option
- command files
- NOLOGO library manager option
- slash (/)
- semicolon, command files
- / command files
ms.assetid: d54f5c81-7147-4b2c-a8db-68ce6eb1eabd
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c8bf42ec1eb4fed681f28cd73b87b3e42b36fe7e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="running-lib"></a>LIB Çalıştırma
LIB denetlemek için çeşitli komut satırı seçenekleri kullanılabilir.  
  
## <a name="lib-command-line"></a>LIB komut satırı  
 LIB çalıştırmak için komutu yazın `lib` seçenekleri ve görev için dosya adları ve ardından LIB gerçekleştirmek için kullandığınız. LIB de aşağıdaki bölümde açıklanan komut dosyalarında komut satırı girişi kabul eder. LIB ortam değişkeni kullanmaz.  
  
> [!NOTE]
>  LINK32.exe alışkındır ve LIB32.exe Microsoft Win32 Yazılım Geliştirme Seti için Windows NT, ya da komut kullanmakta olduğunuz sağlanan araçları `link32 -lib` veya komutu `lib32` kitaplıklarını yönetme ve oluşturma kitaplıkları içeri aktarma. Kullanmak için derleme görevleri dosyaları ve toplu dosyalarınızı değiştirdiğinizden emin olun `lib` yerine komutu.  
  
## <a name="lib-command-files"></a>LIB komut dosyaları  
 Komut satırı bağımsız değişkenleri aşağıdaki sözdizimini kullanarak bir komut dosyasındaki LIB geçirebilirsiniz:  
  
```  
LIB @commandfile  
```  
  
 Dosya `commandfile` bir metin dosyasıdır. Arasında hiç boşluk veya sekmesinde izin at işareti (@) ve dosya adı. Hiçbir varsayılan uzantı yoktur; Her uzantısı dahil tam dosya adını belirtmeniz gerekir. Joker karakterler kullanılamaz. Bir dosya adı ile mutlak veya göreli bir yol belirtebilirsiniz.  
  
 Komut satırında olabildiğince komut dosyasında, boşluk veya sekmelerle, bağımsız değişkenler ayrılabilir; satırbaşı karakterlerini tarafından da ayrılabilir. Bir yorum işaretlemek için noktalı virgül (;) kullanın. LIB satırın sonuna noktalı virgül tüm metni yoksayar.  
  
 Bir komut dosyasında tüm veya komut satırının parçası belirtebilirsiniz ve LIB komutta birden fazla komut dosyası kullanabilirsiniz. Komut satırında o konumda belirtilmiş olması durumunda gibi LIB komut dosyası girişi kabul eder. Komut dosyaları iç içe olamaz. / Nologo seçeneği kullanılmıyorsa LIB komut dosyaları içeriğini görüntülemektedir.  
  
## <a name="using-lib-options"></a>LIB seçeneklerini kullanma  
 İsteğe bağlı bir tire (-) ya da seçenek adında eğik çizgi (/), bir seçenek belirticisi oluşur. Seçenek adları kısaltılmış olamaz. Bazı seçenekler iki nokta (:) sonra belirtilen bir bağımsız değişken alın. Hiçbir boşluk ya da sekme bir seçenek belirtimi içinde izin verilir. Komut satırı seçeneği belirtimlere ayırmak için bir veya daha fazla boşluk ya da sekme kullanın. Seçenek adlarının ve kendi anahtar sözcüğü veya dosya adı bağımsız değişkeni büyük küçük harfe duyarlı değildir, ancak bağımsız değişken olarak kullanılan tanımlayıcıları büyük/küçük harfe duyarlıdır. LIB seçenekleri komut satırında belirtilen sırada ve komut dosyaları işler. Bir seçenek farklı bağımsız değişkenlerle yineleniyorsa işlenmesi için bir öncelik kazanır.  
  
 Aşağıdaki seçenekler LIB tüm modları için geçerlidir:  
  
 / ERRORREPORT [HİÇBİRİ &#124; İSTEM &#124; SIRA &#124; GÖNDERME]  
 Çalışma zamanında lib.exe başarısız olursa, iç bu hatalar hakkında bilgi göndermek için/errorreport kullanabilirsiniz.  
  
 / Errorreport hakkında daha fazla bilgi için bkz: [/errorreport (dahili derleme hatalarını raporla)](../../build/reference/errorreport-report-internal-compiler-errors.md).  
  
 / LTCG  
 Bağlama zamanı kodu oluşturma kullanılarak oluşturulması için kitaplık neden olur.  Daha fazla bilgi için bkz: [/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  
  
 / MACHINE  
 Programın hedef platformu belirtir. Genellikle, /MACHINE belirtmeniz gerekmez. LIB .obj dosyaları makine türünden oluşturur. Ancak, bazı durumlarda, LIB makine türü belirlenemiyor ve bir hata iletisi verir. Böyle bir hata oluşursa, /MACHINE belirtin. / Extract modunda yalnızca doğrulama için bu seçeneği değil. Kullanım `lib /?` kullanılabilir makine türlerini görmek için komut satırında.  
  
 /NOLOGO  
 LIB telif hakkı iletisi ve sürüm numarasını görüntülenmesini engeller ve komut dosyaları Yankı önler.  
  
 / VERBOSE  
 Eklenmekte olan .obj dosya adlarını dahil olmak üzere oturumu ilerlemesini hakkındaki ayrıntıları görüntüler. Bilgiler, standart çıktıya gönderilir ve bir dosyaya yönlendirilebilir.  
  
 /WX [: YOK]  
 Uyarıları hata olarak kabul eder. Bkz: [/WX (Bağlayıcı uyarıları hata olarak değerlendir)](../../build/reference/wx-treat-linker-warnings-as-errors.md) daha fazla bilgi için.  
  
 Diğer seçenekler, yalnızca belirli modları LIB için geçerlidir. Bu seçeneklerin her iki modda açıklayan bölümlerde ele alınmıştır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LIB başvurusu](../../build/reference/lib-reference.md)