---
title: "Bağlayıcı araçları uyarısı LNK4049 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4049
dev_langs: C++
helpviewer_keywords: LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 80a9fbeb3609f10f0f10b050b8e59601045396c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4049"></a>Bağlayıcı Araçları Uyarısı LNK4049
yerel olarak simgesi 'simgesi alındı' tanımlandı  
  
 Simgenin hem dışarı ve programa içeri aktarıldı.  
  
 Kullanarak bir simge bildirme zaman bu uyarı bağlayıcı tarafından oluşturulan `__declspec(dllexport)` depolama sınıfı öznitelik bir nesne dosyasında ve kullanarak referans `__declspec(dllimport)` başka bir öznitelik.  
  
 Uyarısı LNK4049 olduğundan daha genel bir sürümü olan [Bağlayıcı araçları uyarısı LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md). Hangi işlevinden alınan simgenin başvurulan belirleyemediğinde bağlayıcı uyarısı LNK4049 oluşturur.  
  
 LNK4049 yerine LNK4217 oluşturulduğu sık karşılaşılan durumlar şunlardır:  
  
-   Artımlı bağlantılandırma kullanarak gerçekleştirme [/ARTIMLI](../../build/reference/incremental-link-incrementally.md) seçeneği.  
  
-   Kullanarak bütün program iyileştirmesi gerçekleştirme [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) seçeneği.  
  
 LNK4049 çözmek için şunlardan birini deneyin:  
  
-   Kaldırma `__declspec(dllimport)` LNK4049 tetiklemiş simgenin ileriye dönük bildirimi bildiriminden olarak adlandırın. Semboller ikili görüntü içinde kullanarak arayabilirsiniz **DUMPBIN** yardımcı programı. **DUMPBIN/SİMGELERİ** anahtarı görüntünün COFF sembol tablosunu görüntüler. Daha fazla bilgi için **DUMPBIN** yardımcı programı, bkz: [DUMPBIN başvurusu](../../build/reference/dumpbin-reference.md).  
  
-   Artımlı bağlantılandırma ve bütün program iyileştirmesi geçici olarak devre dışı bırakın. Uygulama yeniden derlenmesi alınan simgenin başvurulan işlevin adını içerecek uyarısı LNK4217 oluşturur. Kaldırma `__declspec(dllimport)` bildiriminden alınan simge ve etkinleştir artımlı bağlantılandırma veya bütün program iyileştirmesi gerektiği.  
  
 Son oluşturulan kodun doğru davranacak rağmen içeri aktarılan bir işlevi çağırmak için oluşturulan kodu işlevi doğrudan çağırma daha az verimlidir. Bu uyarı seçeneğini kullanarak derlediğinizde görünmez [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Hakkında daha fazla bilgi almak ve veri bildirimleri dışarı aktarmak için bkz: [dllexport, dllimport](../../cpp/dllexport-dllimport.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki iki modüller bağlama LNK4049 oluşturur. İlk modülü tek bir dışarı aktarılan işlevi içeren bir nesne dosyası oluşturur.  
  
```  
// LNK4049a.cpp  
// compile with: /c  
  
__declspec(dllexport) int func()   
{  
   return 3;  
}  
```  
  
## <a name="example"></a>Örnek  
 İkinci modül içinde bu işlevi çağrısı ile birlikte ilk modülünde dışarı işlevi için ileriye dönük bildirimi içeren bir nesne dosyası oluşturur `main` işlevi. Bu modül ilk modülüyle bağlama LNK4049 oluşturur. Kaldırma `__declspec(dllimport)` bildirimi, uyarı çözümlenir.  
  
```  
// LNK4049b.cpp  
// compile with: /link /WX /LTCG LNK4049a.obj  
// LNK4049 expected  
  
__declspec(dllimport) int func();  
// try the following line instead  
// int func();  
  
int main()  
{  
   return func();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı araçları uyarısı LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)