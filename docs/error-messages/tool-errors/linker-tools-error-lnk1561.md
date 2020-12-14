---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1561'
title: Bağlayıcı Araçları Hatası LNK1561
ms.date: 11/04/2016
f1_keywords:
- LNK1561
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
ms.openlocfilehash: b8c99c6e4b016b1eee443cf8f166665f4f9ad894
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310668"
---
# <a name="linker-tools-error-lnk1561"></a>Bağlayıcı Araçları Hatası LNK1561

giriş noktası tanımlanmalıdır

Bağlayıcı, çalıştırılabilirinizde çağrılacak ilk işlev olan bir *giriş noktası* bulamadı. Varsayılan olarak, bağlayıcı konsol uygulaması için bir `main` veya `wmain` Işlevi, `WinMain` `wWinMain` Windows uygulaması için bir veya işlevi ya da `DllMain` başlatma gerektiren bir dll için arar. [/Entry](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneğini kullanarak başka bir işlev belirtebilirsiniz.

Bu hata birkaç nedenden kaynaklanabilir:

- Bağlanacak dosya listesinde giriş noktanızı tanımlayan dosyayı dahil olmayabilirsiniz. Giriş noktası işlevini içeren dosyanın uygulamanıza bağlı olduğunu doğrulayın.
- Giriş noktasını yanlış işlev imzasını kullanarak tanımlamış olabilirsiniz; Örneğin, işlev adı için yanlış bir büyük/küçük harf kullanmış veya dönüş türü ya da parametre türlerini yanlış bir şekilde belirtmiş olabilirsiniz.
- DLL derlerken [/DLL](../../build/reference/dll-build-a-dll.md) seçeneğini belirtmeyebilirsiniz.
- [/Entry](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneğini kullandığınızda giriş noktası işlevinin adını yanlış bir şekilde belirtmiş olabilirsiniz.
- DLL oluşturmak için [LIB](../../build/reference/lib-reference.md) aracını kullanıyorsanız, bir. def dosyası belirtmiş olabilirsiniz. Bu durumda,. def dosyasını derlemeden kaldırın.

Bir uygulama oluştururken, bağlayıcı, kodunuzu başlatmak üzere çağırmak için bir giriş noktası işlevine bakar. Bu, uygulama yüklendikten ve çalışma zamanı başlatıldıktan sonra çağrılan işlevdir. Bir uygulama için bir giriş noktası işlevi sağlamanız gerekir, aksi, uygulamanız çalışamaz. Bir giriş noktası DLL için isteğe bağlıdır. Varsayılan olarak, bağlayıcı birkaç belirli ad ve imza (gibi) içeren bir giriş noktası işlevine bakar `int main(int, char**)` . /ENTRY bağlayıcı seçeneğini kullanarak, giriş noktası olarak başka bir işlev adı belirtebilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek LNK1561 oluşturur:

```cpp
// LNK1561.cpp
// LNK1561 expected
int i;
// add a main function to resolve this error
```
