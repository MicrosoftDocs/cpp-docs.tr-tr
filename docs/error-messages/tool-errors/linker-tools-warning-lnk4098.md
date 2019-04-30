---
title: Bağlayıcı Araçları Uyarısı LNK4098
ms.date: 03/26/2019
f1_keywords:
- LNK4098
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
ms.openlocfilehash: 66cf1a1bc75405ffc9bae8158bfc8682776a8228
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408101"
---
# <a name="linker-tools-warning-lnk4098"></a>Bağlayıcı Araçları Uyarısı LNK4098

> defaultlib '*Kitaplığı*' ile çakışan diğer kitaplıkların kullanımı; / nodefaultlıb kullanın:*kitaplığı*

Uyumsuz kitaplıklarıyla bağlanmaya çalıştığınız.

> [!NOTE]
> Çalışma zamanı kitaplıkları artık farklı türlerini karıştırmak önlemek için yönergeleri içerir. Bu farklı türleri kullanın veya hata ayıklama çalışırsanız, uyarı ve Çalışma Zamanı Kitaplığı'nın hata ayıklamasız sürümleri aynı programda alırsınız. Örneğin, bir tür bir çalışma zamanı kitaplığı kullanmak için bir dosya ve başka bir tür kullanmak için başka bir dosyaya derlenmişse (örneğin, hata ayıklama Perakende) ve bunları bağlamak için çalıştı, bu uyarı alırsınız. Aynı çalışma zamanı kitaplığı kullanmak için tüm kaynak dosyaları derlemeniz gerekir. Daha fazla bilgi için [/MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md) derleyici seçenekleri.

Bağlayıcı'nın kullanabileceğiniz [: LIB](../../build/reference/verbose-print-progress-messages.md) bağlayıcı arar hangi kitaplıkların Bulunacak anahtar. Örneğin, yürütülebilir dosyanın çok iş parçacıklı, hata ayıklama olmayan çalışma zamanı kitaplıkları kullandığında, bildirilen listesi LIBCMT.lib ve değil Lıbcmtd.lib, MSVCRT.lib veya MSVCRTD.lib içermelidir. Bağlayıcı kullanarak hatalı bir çalışma zamanı kitaplıkları yoksay söyleyebilirsiniz [/nodefaultlıb](../../build/reference/nodefaultlib-ignore-libraries.md) yoksay istediğiniz her bir kitaplık için.

Aşağıdaki tabloda, hangi kitaplıkların bağlı olarak hangi çalışma zamanı kitaplığı kullanmak istediğiniz yoksayılıp yoksayılmaması gerektiğini gösterir. Komut satırında kullanın **/nodefaultlıb** yoksaymak her bir kitaplık için seçenek. Visual Studio IDE'de kitaplıkları noktalı virgül tarafından yok saymak için ayrı **belirli varsayılan kitaplıkları Yoksay** özelliği.

| Bu çalışma zamanı kitaplığını kullanma | Bu kitaplıkları yoksay |
|-----------------------------------|----------------------------|
| Çok iş parçacıklı (LIBCMT.lib) | msvcrt.lib; libcmtd.lib; msvcrtd.lib |
| Çok iş parçacıklı DLL (msvcrt.lib) kullanma | libcmt.lib; libcmtd.lib; msvcrtd.lib |
| Hata ayıklama çok iş parçacıklı (lıbcmtd.lib) | libcmt.lib; msvcrt.lib; msvcrtd.lib |
| Çok iş parçacıklı DLL (msvcrtd.lib) kullanarak hata ayıklama | libcmt.lib; msvcrt.lib; libcmtd.lib |

Örneğin, bu uyarı aldığınızı ve yürütülebilir bir dosya oluşturmak istiyorsanız, çalışma zamanı kitaplıklarının hata ayıklama olmayan, DLL sürümünü kullanan, bağlayıcı ile aşağıdaki seçenekleri kullanabilirsiniz:

```cmd
/NODEFAULTLIB:libcmt.lib NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib
```