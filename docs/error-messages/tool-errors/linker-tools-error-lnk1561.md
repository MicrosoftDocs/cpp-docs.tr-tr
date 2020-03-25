---
title: Bağlayıcı Araçları Hatası LNK1561
ms.date: 11/04/2016
f1_keywords:
- LNK1561
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
ms.openlocfilehash: 706cf6c90dc187b6c343edc82cebb93bb8660452
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194856"
---
# <a name="linker-tools-error-lnk1561"></a>Bağlayıcı Araçları Hatası LNK1561

giriş noktası tanımlanmalıdır

Bağlayıcı, çalıştırılabilirinizde çağrılacak ilk işlev olan bir *giriş noktası*bulamadı. Varsayılan olarak, bağlayıcı konsol uygulaması için bir `main` veya `wmain` işlevi, Windows uygulaması için bir `WinMain` veya `wWinMain` işlevi veya başlatma gerektiren bir DLL için `DllMain` arar. [/Entry](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneğini kullanarak başka bir işlev belirtebilirsiniz.

Bu hata birkaç nedenden kaynaklanabilir:
- Bağlanacak dosya listesinde giriş noktanızı tanımlayan dosyayı dahil olmayabilirsiniz. Giriş noktası işlevini içeren dosyanın uygulamanıza bağlı olduğunu doğrulayın.
- Giriş noktasını yanlış işlev imzasını kullanarak tanımlamış olabilirsiniz; Örneğin, işlev adı için yanlış bir büyük/küçük harf kullanmış veya dönüş türü ya da parametre türlerini yanlış bir şekilde belirtmiş olabilirsiniz.
- DLL derlerken [/DLL](../../build/reference/dll-build-a-dll.md) seçeneğini belirtmeyebilirsiniz.
- [/Entry](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneğini kullandığınızda giriş noktası işlevinin adını yanlış bir şekilde belirtmiş olabilirsiniz.
- DLL oluşturmak için [LIB](../../build/reference/lib-reference.md) aracını kullanıyorsanız, bir. def dosyası belirtmiş olabilirsiniz. Bu durumda,. def dosyasını derlemeden kaldırın.

Bir uygulama oluştururken, bağlayıcı, kodunuzu başlatmak üzere çağırmak için bir giriş noktası işlevine bakar. Bu, uygulama yüklendikten ve çalışma zamanı başlatıldıktan sonra çağrılan işlevdir. Bir uygulama için bir giriş noktası işlevi sağlamanız gerekir, aksi, uygulamanız çalışamaz. Bir giriş noktası DLL için isteğe bağlıdır. Varsayılan olarak, bağlayıcı `int main(int, char**)`gibi birkaç belirli ad ve imza içeren bir giriş noktası işlevi arar. /ENTRY bağlayıcı seçeneğini kullanarak, giriş noktası olarak başka bir işlev adı belirtebilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek LNK1561 oluşturur:

```cpp
// LNK1561.cpp
// LNK1561 expected
int i;
// add a main function to resolve this error
```
