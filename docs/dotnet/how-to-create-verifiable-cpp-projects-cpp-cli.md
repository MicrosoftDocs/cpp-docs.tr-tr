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
ms.openlocfilehash: 36e7ee85d97639df6298a346ae83bb090e81bf87
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704769"
---
# <a name="how-to-create-verifiable-c-projects-ccli"></a>Nasıl yapılır: doğrulanabilir C++ projeleri oluşturma (C + +/ CLI)

Visual C++ Uygulama Sihirbazı doğrulanabilen projeler oluşturmayın.

> [!IMPORTANT]
> Visual Studio 2015 kullanım ve Visual Studio 2017 desteklemiyor **/CLR: pure** ve **/CLR: safe** doğrulanabilen projeler oluşturma. Doğrulanabilen kod gerektiriyorsa, C# kodunuzu Çevir öneririz.

Ancak, destekleyen Visual C++ Derleyici araç setini daha eski bir sürümü kullanıyorsanız **/CLR: pure** ve **/CLR: safe**, projeler doğrulanabilir dönüştürülebilir. Bu konu, proje özelliklerini ayarlamak ve doğrulanabilen uygulamaları oluşturmak için Visual C++ projeleri dönüştürmek için proje kaynak dosyaları değiştirmek açıklar.

## <a name="compiler-and-linker-settings"></a>Derleyici ve bağlayıcı ayarları

 Varsayılan olarak, .NET projeleri/CLR derleyici bayrağını kullanın ve hedef x86 donanım bağlayıcıya yapılandırın. Doğrulanabilen kod/CLR: safe bayrağı kullanmanız gerekir ve yerel makine yönergeler yerine MSIL oluşturmak için bağlayıcı istemeniz gerekir.

### <a name="to-change-the-compiler-and-linker-settings"></a>Derleyici ve bağlayıcı ayarlarını değiştirmek için

1. Proje özellik sayfasını görüntüleyin. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).

1. Üzerinde **genel** altında sayfa **yapılandırma özellikleri** düğüm, kümesi **ortak dil çalışma zamanı desteği** özelliğine **Güvenli MSIL Ortak dil Çalışma zamanı desteği (/ CLR: safe)**.

1. Üzerinde **Gelişmiş** altında sayfa **bağlayıcı** düğüm, kümesi **CLR görüntü türünü** özelliğine **zorla Güvenli IL görüntüsünü (/ CLRIMAGETYPE)**.

## <a name="removing-native-data-types"></a>Yerel veri türlerini kaldırma

Gerçekte kullanımda olsa bile yerel veri türleri doğrulanabilir olduğundan yerel türler içeren tüm üst bilgi dosyaları kaldırmanız gerekir.

> [!NOTE]
> Aşağıdaki yordam Windows Forms uygulaması (.NET) ve konsol uygulaması (.NET) projeler için geçerlidir.

### <a name="to-remove-references-to-native-data-types"></a>Yerel veri türleri başvuruları kaldırmak için

1. Stdafx.h dosyasındaki her şeyin açıklama.

## <a name="configuring-an-entry-point"></a>Bir giriş noktası yapılandırma

Doğrulanabilen uygulamalar C çalışma zamanı kitaplıkları (CRT) kullanamadığından, standart giriş noktası olarak ana işlevi çağırmak için CRT üzerinde bağımlı olamaz. Başka bir deyişle, bağlayıcı başlangıçta çağrılacak işlevin adını açıkça sağlamanız gerekir. (Bu durumda, Main() main() veya _tmain() yerine CRT olmayan giriş noktasını belirtmek için kullanılır, ancak giriş noktası açıkça belirtilmesi gerekir çünkü bu adı isteğe bağlıdır.)

> [!NOTE]
> Aşağıdaki yordamlar konsol uygulaması (.NET) projeler için geçerlidir.

#### <a name="to-configure-an-entry-point"></a>Bir giriş noktası yapılandırmak için

1. Projenin Main.cpp dosyasında Main() _tmain() değiştirin.

1. Proje özellik sayfasını görüntüleyin. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).

1. Üzerinde **Gelişmiş** altında sayfa **bağlayıcı** düğümü girin `Main` olarak **giriş noktası** özellik değeri.

## <a name="see-also"></a>Ayrıca bkz.

- [Saf ve Doğrulanabilen Kod (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)
