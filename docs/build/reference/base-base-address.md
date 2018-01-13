---
title: -BASE (Temel adres) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /base
- VC.Project.VCLinkerTool.BaseAddress
dev_langs: C++
helpviewer_keywords:
- base addresses [C++]
- programs [C++], preventing relocation
- semicolon [C++], specifier
- -BASE linker option
- key address size
- environment variables [C++], LIB
- programs [C++], base address
- LIB environment variable
- BASE linker option
- DLLs [C++], linking
- /BASE linker option
- '@ symbol for base address'
- executable files [C++], base address
- at sign symbol for base address
ms.assetid: 00b9f6fe-0bd2-4772-a69c-7365eb199069
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ddf399757d881484817be676ca3077b4fc21709
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="base-base-address"></a>/BASE (Temel Adres)
```  
/BASE:{address[,size] | @filename,key}  
```  
  
 / TEMEL seçenek bir .exe veya DLL dosyasını varsayılan konumu geçersiz kılma programın taban adresi ayarlar. Bir .exe dosyası için varsayılan taban adresi 0x400000 görüntüleri için 32-bit veya 64-bit görüntüleri 0x140000000 ' dir. Bir DLL için varsayılan taban 0x10000000 görüntüleri için 32-bit veya 64-bit görüntüleri 0x180000000 adresidir. İşletim adres boşluğu düzeni rastgele seçimini (ASLR) desteklemez veya /DYNAMICBASE:NO seçeneği ayarlandığında sistemlerinde işletim sistemi önce bir programı, belirtilen veya varsayılan taban adresi yüklemeyi dener. Sistem, yeterli alan vardır kullanılabilir durumda değilse, programın yeniden yerleştirir. Yeniden konumlandırma engellemek için kullanma [/sabit](../../build/reference/fixed-fixed-base-address.md) seçeneği.  
  
 Bağlayıcı, bir hata verir *adresi* 64 k katı değil. İsteğe bağlı olarak programın boyutunu belirtebilirsiniz; program, belirtilen boyutta sığamıyorsa bağlayıcı bir uyarı verir.  
  
 Komut satırında temel adresini belirtmek için başka bir taban adresi yanıt dosyası kullanarak yoludur. Temel adres yanıt dosyasını temel adresler ve isteğe bağlı boyutları programınızı kullanacağı tüm DLL'ler ve her temel adres için benzersiz bir metin anahtarı içeren bir metin dosyasıdır. Bir yanıt dosyası kullanarak bir taban adresi belirtmek için kullanın bir at işareti (@) yanıt dosyası adından *filename*, virgül, izlenen sonra `key` dosyasında kullanmak temel adres için değer. Bağlayıcı arar *filename* ya da belirtilen yolda, veya yol belirtilmezse LIB ortam değişkeninde belirtilen dizinlerde. Her satırda *filename* bir DLL temsil eder ve sözdizimi aşağıdaki gibidir:  
  
```  
  
key address [size] ;comment  
```  
  
 `key` Bir alfasayısal karakter dizesi ve büyük küçük harfe duyarlı değil. Bu genellikle bir DLL adıdır, ancak olmaması. `key` Bir taban tarafından izlenen *adresi* C dili, onaltılık veya ondalık ve isteğe bağlı bir maksimum `size`. Tüm üç bağımsız değişken, boşluk veya sekmelerle ayrılır. Bağlayıcı, bir uyarı verir belirtilen `size` programın gerektirdiği sanal adres alanı'dan küçük. A `comment` noktalı virgül (;) belirtilen ve aynı ya da ayrı bir satır üzerinde olabilir. Bağlayıcı satırın sonuna noktalı virgül tüm metni yoksayar. Bu örnek, böyle bir dosya parçası gösterir:  
  
```  
main   0x00010000    0x08000000    ; for PROJECT.exe  
one    0x28000000    0x00100000    ; for DLLONE.DLL  
two    0x28100000    0x00300000    ; for DLLTWO.DLL  
```  
  
 Bu satırlar içeren dosyayı DLLS.txt çağrılırsa, bu bilgiler aşağıdaki örnek komut geçerlidir:  
  
```  
link dlltwo.obj /dll /base:@dlls.txt,two  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Güvenlik nedenleriyle, Microsoft, kullanmanızı önerir [/DYNAMICBASE](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) , yürütülebilir dosyaları için taban adresi belirtme yerine seçeneği. Rastgele yükleme zamanında adres alanı düzeni rastgele seçimini (ASLR) özelliği, Windows kullanarak rebased yürütülebilir bir görüntü oluşturur. /DYNAMICBASE seçeneği varsayılan olarak açıktır.  
  
 Taban adresi ayarlamak için başka bir yolu kullanmaktır *temel* bağımsız değişkeninde bir [adı](../../build/reference/name-c-cpp.md) veya [Kitaplığı](../../build/reference/library.md) deyimi. /BASE ve [/dll](../../build/reference/dll-build-a-dll.md) seçenekler birbirine eşit **Kitaplığı** deyimi.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **bağlayıcı** klasör.  
  
3.  Seçin **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **taban adresi** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)