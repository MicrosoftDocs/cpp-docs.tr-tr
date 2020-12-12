---
description: Daha fazla bilgi edinin:/BASE (temel adres)
title: /BASE (Temel Adres)
ms.date: 09/05/2018
f1_keywords:
- /base
- VC.Project.VCLinkerTool.BaseAddress
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
ms.openlocfilehash: 269911c7d9fce47be1b9755ddebf38170ea4e81c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182781"
---
# <a name="base-base-address"></a>/BASE (Temel Adres)

Bir programın temel adresini belirtir.

## <a name="syntax"></a>Syntax

> **/Base:**{*Address*[**,**<em>size</em>] | **\@** <em>dosya adı</em>**,**<em>anahtar</em>}

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Güvenlik nedenleriyle, Microsoft, yürütülebilir dosyalar için temel adresler belirtmek yerine [/DynamicBase](dynamicbase-use-address-space-layout-randomization.md) seçeneğini kullanmanızı önerir. Bu, Windows 'un adres alanı düzeni rastgele seçme (ASLR) özelliğini kullanarak yükleme zamanında rastgele bir şekilde yeniden temel alan yürütülebilir bir görüntü oluşturur. /DYNAMICBASE seçeneği varsayılan olarak açık olur.

/BASE seçeneği, bir. exe veya DLL dosyası için varsayılan konumu geçersiz kılarak, program için bir temel adres ayarlar. Bir. exe dosyasının varsayılan temel adresi 32 bitlik görüntüler için 0x400000 veya 64 bit görüntüler için 0x140000000 şeklindedir. Bir DLL için, varsayılan temel adres 32 bitlik görüntüler için 0x10000000 veya 64 bit görüntüler için 0x180000000 şeklindedir. Adres alanı düzeni rastgele seçimini (ASLR) desteklemeyen işletim sistemlerinde veya/DYNAMICBASE: NO seçeneği belirlenmediğinden, işletim sistemi ilk olarak belirtilen veya varsayılan temel adresli bir programı yüklemeye çalışır. Yeterli kullanılabilir alan yoksa, sistem programı yeniden konumlandırır. Yeniden konumlandırma 'yı engellemek için [/fixed](fixed-fixed-base-address.md) seçeneğini kullanın.

*Adres* 64K 'nın katı değilse bağlayıcı bir hata verir. İsteğe bağlı olarak programın boyutunu belirtebilirsiniz; program belirttiğiniz boyuta uymuyorsa, bağlayıcı bir uyarı verir.

Komut satırında, temel adresi belirtmenin başka bir yolu da temel adres yanıt dosyası kullanmaktır. Temel adres yanıt dosyası, programınızın kullanacağı tüm dll 'Lerin temel adreslerini ve isteğe bağlı boyutlarını ve her temel adres için benzersiz bir metin anahtarını içeren bir metin dosyasıdır. Bir yanıt dosyası kullanarak bir temel adres belirtmek için, bir at işareti ( **\@** ), ardından yanıt dosyasının adı, *Dosya* adı ve ardından virgül, sonra da dosya içinde kullanılacak temel adres için *anahtar* değeri kullanın. Bağlayıcı, belirtilen yolda *dosya adını* arar ya da LIB ortam değişkeninde belirtilen dizinlerde hiçbir yol belirtilmemişse. *Filename* içindeki her satır bir dll 'yi temsil eder ve aşağıdaki sözdizimine sahiptir:

> *anahtar* *adresi* [*size*] **;** *Açıklama*

*Anahtar* alfasayısal karakterlerden oluşan bir dizedir ve büyük/küçük harfe duyarlı değildir. Genellikle bir DLL adıdır, ancak olması gerekmez. *Anahtarın* ardından C dili, onaltılı veya ondalık gösteriminde bir temel *Adres* ve isteğe bağlı en büyük *Boyut* gelir. Üç bağımsız değişken de boşluklarla veya sekmelerle ayrılır. Belirtilen *Boyut* , programın gerektirdiği sanal adres alanından küçükse bağlayıcı bir uyarı verir. *Açıklama* noktalı virgül (**;**) ile belirtilir ve aynı veya ayrı bir satırda olabilir. Bağlayıcı, noktalı virgülden tüm metni satır sonuna kadar yoksayar. Bu örnek, bu dosyanın bir parçasını gösterir:

```
main   0x00010000    0x08000000    ; for PROJECT.exe
one    0x28000000    0x00100000    ; for DLLONE.DLL
two    0x28100000    0x00300000    ; for DLLTWO.DLL
```

Bu satırları içeren dosya DLLS.txt çağrılırsa aşağıdaki örnek komut bu bilgileri uygular:

```
link dlltwo.obj /dll /base:@dlls.txt,two
```

Temel adresi ayarlamaya yönelik başka bir yol da bir [ad](name-c-cpp.md) veya [kitaplık](library.md) deyimindeki *temel* bağımsız değişkeni kullanmaktır. /BASE ve [/DLL](dll-build-a-dll.md) seçenekleri birlikte **LIBRARY** ifadesiyle eşdeğerdir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **Bağlayıcısı**  >  **Gelişmiş** özellik sayfasını seçin.

1. **Temel adres** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
