---
title: "DLL'leri yüklemede gecikme kısıtlamaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.assetid: 0097ff65-550f-4a4e-8ac3-39bf6404f926
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cd3f641a3ac03705ff7f3765d995d5c40bccda7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="constraints-of-delay-loading-dlls"></a>DLL'leri Yüklemede Gecikme Kısıtlamaları
İçeri aktarmalar gecikme yüklenmesi ile ilgili kısıtlamalar vardır.  
  
-   Veri aktarımlarının desteklenemiyor. Açıkça işlemek için geçici bir çözüm olan verileri kullanarak kendiniz içeri `LoadLibrary` (veya `GetModuleHandle` Gecikmeli Yükleme Yardımcısı DLL yüklü öğrendikten sonra) ve `GetProcAddress`.  
  
-   Kernel32.dll Gecikmeli yükleme desteklenmez. Bu DLL yüklenirken gecikme gerçekleştirmek gecikme yükü Yardımcısı yordamları için gereklidir.  
  
-   [Bağlama](../../build/reference/binding-imports.md) girişi iletilir noktaları desteklenmiyor.  
  
-   Gecikmeli yüklenen DLL'i giriş noktası ortaya işlem içi başlatmaları varsa DLL gecikme yüklenmesini işleminin aynı davranışı sağlamayabilir. Diğer durumlarda kullanılarak bildirilen statik TLS (iş parçacığı yerel depolaması), dahil [__declspec(thread)](../../cpp/thread.md), hangi işlenmez aracılığıyla DLL yüklendiğinde `LoadLibrary`. Kullanarak dinamik TLS `TlsAlloc`, `TlsFree`, `TlsGetValue`, ve `TlsSetValue`, statik ya da Gecikmeli yüklenen DLL'ler kullanıma hazırdır.  
  
-   Statik (Genel) işlev işaretçileri içeri aktarılan işlevler için işlev ilk çağrısından sonra yeniden. İşlev işaretçisi ilk kez kullanıyorsanız dönüştürücü işaret edecek olmasıdır.  
  
-   Şu anda normal alma mekanizması kullanırken yalnızca belirli yordamları DLL'den yüklenmesini geciktirmek için bir yolu yoktur.  
  
-   Özel çağırma kuralları (örneğin x86 üzerinde durum kodlarını kullanarak mimarileri) desteklenmez. Ayrıca, kayan nokta yazmaçlar herhangi bir platformda kaydedilmez. Kayan nokta türleri özel yardımcı yordamın veya kanca yordamları kullanırsanız, tamamen kaydetmek ve çağırma kuralları kayan nokta parametrelerle kaydı ile makinelerde kayan nokta durumunu geri yüklemek ihtiyaç duyar. Yardım işlevi sayısal veri işlemcisi (NDP'nin) yığınında kayan nokta parametreleri yap CRT işlevleri çağırırsanız CRT DLL dosyasını yüklerken gecikmesi hakkında dikkatli olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gecikmeli yüklenen DLL'ler için bağlayıcı desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)   
 [LoadLibrary işlevi](http://msdn.microsoft.com/library/windows/desktop/ms684175.aspx)   
 [GetModuleHandle işlevi](http://msdn.microsoft.com/library/windows/desktop/ms683199.aspx)   
 [GetProcAddress işlevi](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx)   
 [TlsAlloc işlevi](http://msdn.microsoft.com/library/windows/desktop/ms686801.aspx)   
 [TlsFree işlevi](http://msdn.microsoft.com/library/windows/desktop/ms686804.aspx)   
 [TlsGetValue işlevi](http://msdn.microsoft.com/library/windows/desktop/ms686812.aspx)   
 [TlsSetValue işlevi](http://msdn.microsoft.com/library/windows/desktop/ms686818.aspx)