---
title: BSCMAKE seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCBscMakeTool.OutputFile
- VC.Project.VCBscMakeTool.SuppressStartupBanner
- VC.Project.VCBscMakeTool.PreserveSBR
dev_langs:
- C++
helpviewer_keywords:
- /v BSCMAKE option
- Iu BSCMAKE option
- browse information files (.bsc), content
- /Er BSCMAKE option
- NOLOGO BSCMAKE option
- /s BSCMAKE option
- /Ei BSCMAKE option
- /o BSCMAKE option
- /NOLOGO BSCMAKE option
- /Iu BSCMAKE option
- s BSCMAKE option (/s)
- /Em BSCMAKE option
- Em BSCMAKE option
- Es BSCMAKE option
- files [C++], BSCMAKE
- Er BSCMAKE option
- BSCMAKE, options for controlling files
- controlling BSCMAKE options
- El BSCMAKE option
- /El BSCMAKE option
- /Es BSCMAKE option
- Ei BSCMAKE option
ms.assetid: fa2f1e06-c684-41cf-80dd-6a554835ebd2
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 46c258a5591615bb277823ccc5261fade3c5e2af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-options"></a>BSCMAKE Seçenekleri
Bu bölümde BSCMAKE denetlemek için kullanılabilen seçenekler açıklanmaktadır. Çeşitli seçenekler gözatma bilgileri dosyası içeriğini hariç veya belirli bilgiler dahil olmak üzere denetler. Dışlama seçenekleri BSCMAKE daha hızlı çalışmasına izin verebilir ve daha küçük bir .bsc dosyasında neden olabilir. Seçenek adları büyük küçük harfe duyarlı (dışında **/Yardım** ve **/nologo**).  
  
 Yalnızca **/nologo** ve **/o** Visual Studio geliştirme ortamında kullanılabilir.  Bkz: [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md) hakkında bilgi için bir projenin özellik sayfaları erişim.  
  
 /Ei ( `filename`...)  
 Belirtilen INCLUDE dosyaların içeriğini gözatma bilgileri dosyasından dışlar. Birden çok dosya belirtmek için adları boşlukla ayırın ve liste parantez içine alın. Parantez tek belirtirseniz, gerekli olmayan `filename`. Kullanım **/Ei** ile birlikte **/Es** tarafından dışarıda dosyaları dışarıda bırak seçeneği **/Es**.  
  
 /El  
 Yerel semboller dışlar. Varsayılan yerel semboller eklemektir. Yerel semboller hakkında daha fazla bilgi için bkz: [.sbr dosyası oluşturma](../../build/reference/creating-an-dot-sbr-file.md).  
  
 /Em  
 Simgeler makroları gövdesinde dışlar. Kullanım **/Em** yalnızca makroları adlarını Gözat bilgileri dosyasına eklenecek. Makro adları ve makrosu genişletmeler sonucu dahil etmek için varsayılandır.  
  
 /Er ( `symbol`...)  
 Belirtilen simgeler gözatma bilgileri dosyasından dışlar. Birden çok sembol adları belirtmek için adlarının boşlukla ayırın ve liste parantez içine alın. Parantez tek belirtirseniz, gerekli olmayan `symbol`.  
  
 /ES  
 Gözatma bilgileri dosyasından INCLUDE ortam değişkeninde belirtilen mutlak bir yol bulunamadı ya da mutlak bir yol ile belirtilen her içerme dosyası dışlar. (Sistem genellikle, bunlar çok miktarda Gözat bilgi dosyanızda gerekmeyebilir bilgisi içeren dosyaları içerir.) Bu seçenek, belirtilen yol olmadan veya göreli yollar veya INCLUDE göreli yolda bulunan dosyalarla dosyaları dışarıda değil. Kullanabileceğiniz **/Ei** ile birlikte seçeneği **/Es** hariç tutulacak dosyalar **/Es** hariç tutmaz. Yalnızca bazı dosyaları dışarıda bırakmak istiyorsanız, **/Es** hariç kullanmak **/Ei** yerine **/Es** ve dışlamak istediğiniz dosyaların listesi.  
  
 / errorreport: [hiçbiri &#124; istemi &#124; sıra &#124; gönderme]  
 Bscmake.exe iç hatalara ilişkin bilgileri Microsoft'a göndermek olanak sağlar.  
  
 Daha fazla bilgi için **/errorreport**, bkz: [/errorreport (dahili derleme hatalarını raporla)](../../build/reference/errorreport-report-internal-compiler-errors.md).  
  
 / HELP  
 BSCMAKE komut satırı sözdizimi özetini görüntüler.  
  
 /IU  
 Başvurulmayan simgeleri içerir. Varsayılan olarak, BSCMAKE tanımlı, ancak yapılmayan simgeleri kaydetmez. .Sbr dosyası paketlenmiş, derleyici başvurulmayan simgeleri zaten kaldırıldığından bu seçenek, giriş dosyası için etkisi yoktur.  
  
 /n  
 Nonincremental derleme zorlar. Kullanım  **/n**  olsun veya olmasın .bsc dosyası var. gözatma bilgileri dosyası tam derlemesinde zorlamak için ve kesilmiş gelen .sbr dosyaları engellemek için. Bkz: [BSCMAKE .bsc dosyasını nasıl derler](../../build/reference/how-bscmake-builds-a-dot-bsc-file.md).  
  
 /NOLOGO  
 BSCMAKE telif hakkı iletisi gizler.  
  
 /o`filename`  
 Gözatma bilgileri dosyası için bir ad belirtir. Varsayılan olarak, BSCMAKE ilk .sbr dosyası ve bir .bsc uzantısı temel adı gözatma bilgileri dosyası sağlar.  
  
 / S ( `filename`...)  
 BSCMAKE belirtilen içerme dosyası, karşılaşılan ilk kez işlemek ve aksi takdirde dışlanacak söyler. Ne zaman bir dosya (örneğin, bir üst bilgi veya .h, bir .c için veya .cpp kaynak dosyası) birkaç kaynak dosyalarına dahil, ancak her zaman yönergeleri'ön işleme değişmeden işleme süresi kaydetmek için bu seçeneği kullanın. Oluşturmakta olduğunuz gözatma bilgileri dosyası için önemli bir yolla bir dosya değiştirildiğinde bu seçeneği kullanmak isteyebilirsiniz. Birden çok dosya belirtmek için adları boşlukla ayırın ve liste parantez içine alın. Parantez tek belirtirseniz, gerekli olmayan `filename`. Dahil edilen her zaman bir dosyayı dışlamak istiyorsanız kullanın **/Ei** veya **/Es** seçeneği.  
  
 /v  
 İşlenmekte olan her .sbr dosyası adını ve Çalıştır tam BSCMAKE hakkında bilgi içeren ayrıntılı çıktı sağlar.  
  
 /?  
 BSCMAKE komut satırı sözdizimi kısa bir özetini görüntüler.  
  
 Aşağıdaki komut satırını MAIN.bsc tam derlemesinde üç .sbr dosyaları yapmak için BSCMAKE söyler. Ayrıca, TOOLBOX.h birden çok tekrarı dışlanacak BSCMAKE bildirir:  
  
```  
BSCMAKE /n /S toolbox.h /o main.bsc file1.sbr file2.sbr file3.sbr  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BSCMAKE Başvurusu](../../build/reference/bscmake-reference.md)