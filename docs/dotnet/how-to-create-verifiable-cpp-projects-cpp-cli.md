---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: doğrulanabilir C++ projeleri oluşturma (C++/CLı)'
title: 'Nasıl yapılır: Doğrulanabilir C++ Projeleri Oluşturma (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- verifiable assemblies [C++], creating
- conversions, C++ projects
- Visual Studio C++ projects
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
ms.openlocfilehash: 5f3a84a4f87db5cf390dcfbad18f167108e0ff08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245999"
---
# <a name="how-to-create-verifiable-c-projects-ccli"></a>Nasıl yapılır: doğrulanabilir C++ projeleri oluşturma (C++/CLı)

Visual C++ uygulama sihirbazları doğrulanabilir projeler oluşturmaz.

> [!IMPORTANT]
> Visual Studio 2015 kullanım dışı ve Visual Studio 2017, **/clr: Pure** ve **/clr:** doğrulanabilir projelerin güvenli bir şekilde oluşturulmasını desteklemez. Doğrulanabilir koda ihtiyacınız varsa kodunuzu C# ' a çevirmeniz önerilir.

Ancak, Microsoft C++ derleyici araç takımının **/clr: Pure** ve **/clr: Safe**' i destekleyen eski bir sürümünü kullanıyorsanız, projeleri doğrulanabilir olacak şekilde dönüştürülebilirler. Bu konuda, proje özelliklerinin nasıl ayarlanacağı ve proje kaynak dosyalarının, doğrulanabilen uygulamalar oluşturmak için Visual Studio C++ projelerinizi dönüştürmek üzere nasıl değiştirileceği açıklanır.

## <a name="compiler-and-linker-settings"></a>Derleyici ve bağlayıcı ayarları

Varsayılan olarak, .NET projeleri/clr derleyici bayrağını kullanır ve bağlayıcıyı, x86 donanımını hedeflemek için yapılandırır. Doğrulanabilen kod için/clr: Safe bayrağını kullanmanız gerekir ve bağlayıcıya yerel makine yönergeleri yerine MSIL oluşturmak için talimat vermelisiniz.

### <a name="to-change-the-compiler-and-linker-settings"></a>Derleyici ve bağlayıcı ayarlarını değiştirmek için

1. Proje özellik sayfasını görüntüleyin. Daha fazla bilgi için bkz. [derleyici ve derleme özelliklerini ayarlama](../build/working-with-project-properties.md).

1. **Yapılandırma özellikleri** düğümünün altındaki **genel** sayfasında, **ortak dil çalışma zamanı desteği** özelliğini **Güvenli MSIL ortak dil çalışma zamanı desteği (/clr: Safe)** olarak ayarlayın.

1. **Bağlayıcı** düğümünün altındaki **Gelişmiş** sayfasında, **clr görüntü türü** özelliğini **güvenli Il görüntüsünü zorlamak için ayarlayın (/clrimagetype: Safe)**.

## <a name="removing-native-data-types"></a>Yerel veri türleri kaldırılıyor

Yerel veri türleri doğrulanabilir olmadığından, gerçekten kullanılmasa bile, yerel türler içeren tüm üst bilgi dosyalarını kaldırmanız gerekir.

> [!NOTE]
> Aşağıdaki yordam Windows Forms uygulaması (.NET) ve konsol uygulaması (.NET) projeleri için geçerlidir.

### <a name="to-remove-references-to-native-data-types"></a>Yerel veri türlerine yönelik başvuruları kaldırmak için

1. Stbafx. h dosyasındaki her şeyi açıklama olarak yapın.

## <a name="configuring-an-entry-point"></a>Giriş noktası yapılandırma

Doğrulanabilen uygulamalar C çalışma zamanı kitaplıklarını (CRT) kullanamadığından, ana işlevi standart giriş noktası olarak çağırmak için CRT 'ya bağlı olamaz. Bu, başlangıçta bağlayıcıya çağrılacak işlevin adını açıkça sağlamanız gerektiği anlamına gelir. (Bu durumda, bir CRT olmayan giriş noktası belirtmek için Main () veya _tmain () yerine Main () kullanılır, ancak giriş noktasının açık olarak belirtilmesi gerektiğinden, bu ad rastgele olur.)

> [!NOTE]
> Aşağıdaki yordamlar konsol uygulaması (.NET) projeleri için geçerlidir.

#### <a name="to-configure-an-entry-point"></a>Bir giriş noktası yapılandırmak için

1. Projenin Main. cpp dosyasında _tmain () öğesini Main () olarak değiştirin.

1. Proje özellik sayfasını görüntüleyin. Daha fazla bilgi için bkz. [derleyici ve derleme özelliklerini ayarlama](../build/working-with-project-properties.md).

1. **Bağlayıcı** düğümünün altındaki **Gelişmiş** sayfasında `Main` **giriş noktası** Özellik değeri olarak girin.

## <a name="see-also"></a>Ayrıca bkz.

- [Saf ve Doğrulanabilen Kod (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)
