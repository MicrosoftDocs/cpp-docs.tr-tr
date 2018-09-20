---
title: 'Nasıl yapılır: doğrulanabilir C++ projeleri oluşturma (C + +/ CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- verifiable assemblies [C++], creating
- conversions, C++ projects
- Visual C++ projects
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a84fcd660f8cc7ef5686fe0e03f9b520d1251bc4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408940"
---
# <a name="how-to-create-verifiable-c-projects-ccli"></a>Nasıl yapılır: doğrulanabilir C++ projeleri oluşturma (C + +/ CLI)

Visual C++ uygulama sihirbazları doğrulanabilir projeleri oluşturabilirsiniz.

> [!IMPORTANT]
> Visual Studio 2015 kullanım dışı ve Visual Studio 2017'yi desteklemez **/CLR: pure** ve **/CLR: safe** doğrulanabilir projeleri oluşturma. Doğrulanabilen kod gerekiyorsa, C# kodunuzda Çevir öneririz.

Ancak, destekleyen Visual C++ Derleyici araç setini daha eski bir sürümünü kullanıyorsanız **/CLR: pure** ve **/CLR: safe**, projeleri doğrulanabilir dönüştürülebilir. Bu konuda, proje özelliklerini ayarlama ve doğrulanabilir uygulamalar oluşturmak için Visual C++ projeleriniz dönüştürmek için proje kaynak dosyalarında değişiklik açıklar.

## <a name="compiler-and-linker-settings"></a>Derleyici ve bağlayıcı ayarları

Varsayılan olarak, .NET projeleri, / CLR derleyici bayrağını kullanın ve hedef x86 donanım bağlayıcıya yapılandırın. Doğrulanabilir kod için/CLR: safe bayrağı kullanmanız gerekir ve yerel makine yönergelerine yerine MSIL oluşturma konusunda talimat vermelisiniz.

### <a name="to-change-the-compiler-and-linker-settings"></a>Derleyici ve bağlayıcı ayarları değiştirmek için

1. ' % S'proje özelliği sayfasında görüntüler. Daha fazla bilgi için [Working with Project Properties](../ide/working-with-project-properties.md).

1. Üzerinde **genel** altındaki **yapılandırma özellikleri** , düğüm kümesi **ortak dil çalışma zamanı desteği** özelliğini **Güvenli MSIL Ortak dil Çalışma zamanı desteği (/ CLR: safe)**.

1. Üzerinde **Gelişmiş** altındaki **bağlayıcı** , düğüm kümesi **CLR imaj türü** özelliğini **Güvenli IL imajını zorla (/ CLRIMAGETYPE: safe)**.

## <a name="removing-native-data-types"></a>Yerel veri türlerini kaldırma

Yerel veri türleri doğrulanabilir olduğundan, aslında kullanılmazlar bile yerel türler içeren tüm üst bilgi dosyaları kaldırmanız gerekir.

> [!NOTE]
> Aşağıdaki yordam Windows Forms uygulaması (.NET) ve konsol uygulaması (.NET) projeler için geçerlidir.

### <a name="to-remove-references-to-native-data-types"></a>Yerel veri türleri başvuruları kaldırmak için

1. Stdafx.h dosyadaki her şeyi açıklama.

## <a name="configuring-an-entry-point"></a>Bir giriş noktası yapılandırma

C çalışma zamanı kitaplıkları (CRT) doğrulanabilir uygulamaları kullanamazsınız çünkü ana işlevi standart giriş noktası olarak çağırmak için CRT üzerinde bağımlı olamaz. Başka bir deyişle, açıkça için bağlayıcı başlangıçta çağrılacak işlevin adını sağlamanız gerekir. (Bu durumda, Main() main() veya _tmain() yerine bir CRT olmayan giriş noktasını belirtmek için kullanılan, ancak giriş noktası açıkça belirtilmesi gerektiğinden, bu rastgele bir addır.)

> [!NOTE]
> Aşağıdaki yordamlar, konsol uygulaması (.NET) projeler için geçerlidir.

#### <a name="to-configure-an-entry-point"></a>Bir giriş noktası yapılandırmak için

1. _Tmain() Main() projenin ana .cpp dosyası ile değiştirin.

1. ' % S'proje özelliği sayfasında görüntüler. Daha fazla bilgi için [Working with Project Properties](../ide/working-with-project-properties.md).

1. Üzerinde **Gelişmiş** altındaki **bağlayıcı** düğümünü girin `Main` olarak **giriş noktası** özellik değeri.

## <a name="see-also"></a>Ayrıca bkz.

- [Saf ve Doğrulanabilen Kod (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)
