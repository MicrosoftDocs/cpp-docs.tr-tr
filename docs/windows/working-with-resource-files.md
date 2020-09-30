---
title: Kaynak dosyalarla çalışma (C++)
ms.date: 02/14/2019
helpviewer_keywords:
- resources [C++], about resources
- resources [C++], about resource files
- resource files [C++], about resource files
ms.assetid: 2699a539-b369-4b78-80f0-df03eb7b6780
ms.openlocfilehash: 3e387a1cefb6577760a34c7957d4f5019b1d49ef
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502904"
---
# <a name="working-with-resource-files"></a>Kaynak Dosyalarıyla Çalışma

> [!WARNING]
> Bu bölüm, C++ dilinde yazılmış Windows Masaüstü uygulamaları için geçerlidir.
>
> C++ dilinde yazılan Evrensel Windows Platformu uygulamalardaki kaynaklarla ilgili bilgiler için bkz. [uygulama kaynaklarını tanımlama](/windows/uwp/app-resources/)veya c++/CLI (yönetilen) projelerine kaynak ekleme hakkında bilgi için, bkz. .NET Framework Geliştirici Kılavuzu 'Ndaki [masaüstü uygulamalarında kaynaklar](/dotnet/framework/resources/index) .

Kaynaklar, şunun gibi geniş bir dizi öğeden oluşabilir:

- Kullanıcıya bir bit eşlem, simge veya imleç gibi bilgiler sağlayan arabirim öğeleri.
- Veri ve uygulama gereksinimlerini içeren özel kaynaklar.
- Kurulum API 'Leri tarafından kullanılan sürüm kaynakları.
- Menü ve iletişim kutusu kaynakları.

Projenize yeni kaynaklar ekleyebilir ve bu kaynakları uygun kaynak düzenleyicisini kullanarak değiştirebilirsiniz. Çoğu Visual C++ sihirbaz, projeniz için otomatik olarak bir. rc dosyası oluşturacaktır.

> [!NOTE]
> **Kaynak düzenleyicileri** ve **kaynak görünümü** Express sürümlerinde kullanılamaz.

Kaynak dosyalarını yönetilen projelere el ile eklemek için bkz. [Masaüstü uygulamaları Için kaynak dosyaları oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Bu makale, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama özelliklerini içerir.

Yönetilen uygulamalardaki kaynakları globalize ve yerelleştirmek için bkz. [uygulamaları Genelleştirme ve yerelleştirme .NET Framework](/dotnet/standard/globalization-localization/index).

## <a name="in-this-section"></a>Bu Bölümde

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
Kaynak dosyalarını ve bunların Windows masaüstü uygulamalarında nasıl kullanıldığını açıklar. Ayrıca, kaynak dosyalarının nasıl kullanılacağını betimleyen makalelere bağlantılar sağlar.

[Kaynak tanımlayıcıları (semboller)](../windows/symbols-resource-identifiers.md)<br/>
Sembolleri açıklar ve projelerinizde sembolleri yönetmek için **kaynak sembolleri** iletişim kutusunu kullanma hakkında bilgi sağlar.

[Kaynak düzenleyicileri](../windows/resource-editors.md)<br/>
Visual Studio 'da sunulan kaynak düzenleyicilerini ve her düzenleyicide değiştirebileceğiniz kaynak türlerini açıklar. Ayrıca, her bir düzenleyiciyi kullanma hakkında ayrıntılı bilgi için bağlantılar sağlar.

## <a name="related-sections"></a>İlgili Bölümler

[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md)<br/>
Visual C++ belgelerine ilişkin bağlantıları sağlar.

[Bizimle iletişime geçin](/visualstudio/ide/talk-to-us)<br/>
Belge kümesini kullanma, ürün desteğiyle iletişim kurma ve erişilebilirlik özelliklerini kullanma hakkındaki bilgilere bağlantılar sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Windows Masaüstü uygulamaları](./desktop-applications-visual-cpp.md)<br/>
[Menüler ve diğer kaynaklar](/windows/win32/menurc/resources)
