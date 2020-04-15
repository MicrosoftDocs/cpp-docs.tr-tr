---
title: Bağlayıcı Araçları Hatası LNK1561
ms.date: 11/04/2016
f1_keywords:
- LNK1561
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
ms.openlocfilehash: b397ef8e551f8cd6179392541e35183a5850454f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81357746"
---
# <a name="linker-tools-error-lnk1561"></a>Bağlayıcı Araçları Hatası LNK1561

giriş noktası tanımlanmalıdır

Bağlayıcı bir *giriş noktası*bulamadı, ilk işlevi çalıştırılabilir aramak için. Varsayılan olarak, bağlayıcı bir `main` konsol `wmain` uygulaması, bir Windows `WinMain` `wWinMain` uygulaması için bir işlev `DllMain` veya başlatma gerektiren bir DLL için bir işlev arar. [/ENTRY](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneğini kullanarak başka bir işlev belirtebilirsiniz.

Bu hatanın birkaç nedeni olabilir:

- Bağlantı için dosyalar listesine giriş noktanızı tanımlayan dosyayı eklememiş olabilirsiniz. Giriş noktası işlevini içeren dosyanın uygulamanıza bağlı olduğunu doğrulayın.
- Giriş noktasını yanlış işlev imzasını kullanarak tanımlamış olabilirsiniz; örneğin, işlev adı için yanlış yazılmış veya yanlış örnek kullanmış veya dönüş türünü veya parametre türlerini yanlış belirtmiş olabilirsiniz.
- Bir DLL yaparken [/DLL](../../build/reference/dll-build-a-dll.md) seçeneğini belirtmemiş olabilirsiniz.
- [/ENTRY](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneğini kullandığınızda giriş noktası işlevinin adını yanlış belirtmiş olabilirsiniz.
- Bir DLL oluşturmak için [LIB](../../build/reference/lib-reference.md) aracını kullanıyorsanız, bir .def dosyası belirtmiş olabilirsiniz. Bu ysa, .def dosyasını yapıdan kaldırın.

Bir uygulama inşa ederken, bağlayıcı kodunuzu başlatmak için aramak için bir giriş noktası işlevi arar. Bu, uygulama yüklendikten ve çalışma süresi başharfe bindirildikten sonra çağrılan işlevdir. Bir uygulama için bir giriş noktası işlevi sağlamanız gerekir, yoksa uygulamanız çalıştırılamıyor. Bir giriş noktası DLL için isteğe bağlıdır. Varsayılan olarak, bağlayıcı gibi birkaç özel ad ve imzabiri olan bir giriş `int main(int, char**)`noktası işlevi arar. /ENTRY bağlayıcı seçeneğini kullanarak giriş noktası olarak başka bir işlev adı belirtebilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek LNK1561 oluşturur:

```cpp
// LNK1561.cpp
// LNK1561 expected
int i;
// add a main function to resolve this error
```
