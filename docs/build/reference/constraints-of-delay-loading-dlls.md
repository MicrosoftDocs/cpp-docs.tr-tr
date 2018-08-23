---
title: DLL'leri yüklemede gecikme kısıtlamaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.assetid: 0097ff65-550f-4a4e-8ac3-39bf6404f926
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40774d6307eb9b423ebd4fd303a48acbd87eda24
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2018
ms.locfileid: "42464992"
---
# <a name="constraints-of-delay-loading-dlls"></a>DLL'leri Yüklemede Gecikme Kısıtlamaları
İçeri aktarmalar Gecikmeli yüklenmesi ile ilgili kısıtlamalar vardır.  
  
-   Veri içeri aktarmaları desteklenemez. Açıkça işlemek için geçici bir çözüm olan verileri kullanarak kendiniz almak `LoadLibrary` (veya `GetModuleHandle` DLL gecikme yükleme yardımcı yüklediğini öğrendikten sonra) ve `GetProcAddress`.  
  
-   Gecikmeli yükleme Kernel32.dll desteklenmiyor. Bu DLL için Gecikmeli Yükleme Yardımcısı rutinleri Gecikmeli yükleme gerçekleştirmek gerekli değildir.  
  
-   [Bağlama](../../build/reference/binding-imports.md) girişi iletilen noktaları desteklenmez.  
  
-   Gecikmeli yüklenen DLL giriş noktası oluşan işlem başına başlatmalar varsa bir DLL gecikme yükleme işleminin aynı davranışa neden olabilir değil. Kullanılarak bildirilen statik TLS (iş parçacığı yerel depolama), diğer durumlar [gt;__declspec(thread)](../../cpp/thread.md), hangi işlenmez aracılığıyla DLL yüklendiğinde `LoadLibrary`. Kullanarak dinamik TLS `TlsAlloc`, `TlsFree`, `TlsGetValue`, ve `TlsSetValue`, statik veya Gecikmeli yüklenen DLL'ler için hala kullanılabilir.  
  
-   İçeri aktarılan işleve (Genel) statik işlev işaretçileri ilk işlev çağrısından sonra başlatılmasına. İşlev işaretçisi, ilk kullanım için dönüştürücü işaret edecek olmasıdır.  
  
-   Şu anda normal alma mekanizması kullanırken yalnızca belirli yordamları DLL'in yüklenmesini geciktirmek için hiçbir yolu yoktur.  
  
-   Özel çağırma kuralları (üzerinde x86 koşul kodları kullanma gibi mimarileri) desteklenmez. Ayrıca, kayan nokta kayıtlarını herhangi bir platformda kaydedilmez. Özel yardımcı yordamı veya kanca rutinleri kayan nokta türleri kullanıyorsanız, bunlar tamamen kaydetmek ve çağırma kuralları kayan nokta parametrelerle yazmaç ile makinelerde kayan nokta durumu geri yükleme gerekir. Bir sayısal veri işlemcisi (NDP) yığınında Yardım işlevinde kayan nokta parametre alan CRT işlevleri çağırırsanız, CRT DLL yükleme gecikmesi hakkında dikkatli olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gecikmeli yüklenen DLL'ler için bağlayıcı desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)   
 [LoadLibrary işlevi](http://msdn.microsoft.com/library/windows/desktop/ms684175.aspx)   
 [GetModuleHandle işlevi](http://msdn.microsoft.com/library/windows/desktop/ms683199.aspx)   
 [GetProcAddress işlevi](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx)   
 [TlsAlloc işlevi](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc)   
 [TlsFree işlevi](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsfree)   
 [TlsGetValue işlevi](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)   
 [TlsSetValue işlevi](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlssetvalue)