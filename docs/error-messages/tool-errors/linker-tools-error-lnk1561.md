---
title: Bağlayıcı araçları hatası LNK1561 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1561
dev_langs:
- C++
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac24ed0c4aff4cbd7f0ea95ff71d0b8c4b3be09c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050768"
---
# <a name="linker-tools-error-lnk1561"></a>Bağlayıcı Araçları Hatası LNK1561

Giriş noktası tanımlanmalıdır

Bağlayıcı bulunamadı bir *giriş noktası*, yürütülebilir dosyanın içinde çağırmak için başlangıç işlevi. Varsayılan olarak, bağlayıcı arayan bir `main` veya `wmain` işlevi bir konsol uygulaması için bir `WinMain` veya `wWinMain` işlevi bir Windows uygulaması için veya `DllMain` başlatma gerektiren bir DLL için. Başka bir işlevi kullanarak belirtebilirsiniz [/Entry](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneği.

Bu hatanın birkaç nedeni olabilir:
- Giriş noktasına bağlamak için dosya listesinde tanımlayan dosyayı eklememiş olabilirsiniz. Giriş noktası işlevini içeren dosyayı uygulamanıza bağlı olduğundan emin olun.
- Yanlış işlev imzası kullanarak giriş noktası tanımlanmış; Örneğin, yanlış yazılmış veya yanlış durumda işlevi adı için kullanılan veya olabilirsiniz dönüş türü veya parametre türleri yanlış belirtildi.
- Siz değil belirtmiş olabilirsiniz [/dll](../../build/reference/dll-build-a-dll.md) bir DLL derlenirken seçeneği.
- Kullandığınız zaman, giriş noktası işlevini adı yanlış belirtmiş olabilirsiniz [/Entry](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneği.
- Kullanıyorsanız [LIB](../../build/reference/lib-reference.md) bir DLL yapılandırmak için aracı, .def dosyası belirtmiş olabilirsiniz. Bu durumda, .def dosyası derlemeden kaldırın.

Bir uygulama oluştururken, bağlayıcı için giriş noktası işlevini kodunuzu başlatmak için çağrılacak arar. Uygulama yüklendikten ve çalışma zamanı başlatıldıktan sonra çağrılan işlev budur. Bir uygulama için giriş noktası işlevini belirtmeniz gerekir veya uygulamanızı çalıştıramazsınız. Bir giriş noktası bir DLL için isteğe bağlıdır. Varsayılan olarak, bağlayıcı gibi birkaç belirli adlar ve imzalar, birine sahip bir giriş noktası işlevini için görünür `int main(int, char**)`. Başka bir işlev adı girişi olarak belirtebilirsiniz/Entry bağlayıcı seçeneğini kullanarak noktası.

## <a name="example"></a>Örnek

Aşağıdaki örnek, LNK1561 oluşturur:

```cpp
// LNK1561.cpp
// LNK1561 expected
int i;
// add a main function to resolve this error
```