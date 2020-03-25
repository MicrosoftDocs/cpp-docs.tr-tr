---
title: Kaynak dosyalarla çalışma (C++)
ms.date: 02/14/2019
helpviewer_keywords:
- resources [C++], about resources
- resources [C++], about resource files
- resource files [C++], about resource files
ms.assetid: 2699a539-b369-4b78-80f0-df03eb7b6780
ms.openlocfilehash: 142a9120e0b6b95e659fcb47c275653fbefd8cbe
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165892"
---
# <a name="working-with-resource-files"></a>Kaynak Dosyalarıyla Çalışma

> [!WARNING]
> Bu bölüm, içinde C++yazılmış Windows Masaüstü uygulamaları için geçerlidir.
>
> İçinde C++yazılan Evrensel Windows platformu uygulamalardaki kaynaklarla ilgili bilgiler için bkz. [uygulama kaynaklarını tanımlama](/windows/uwp/app-resources/)veya C++/CLI (yönetilen) projelerine kaynak ekleme hakkında bilgi Için, bkz. .NET Framework Geliştirici Kılavuzu 'ndaki [masaüstü uygulamalarında kaynaklar](/dotnet/framework/resources/index) .

Kaynaklar, şunun gibi geniş bir dizi öğeden oluşabilir:

- Kullanıcıya bir bit eşlem, simge veya imleç gibi bilgiler sağlayan arabirim öğeleri.
- Veri ve uygulama gereksinimlerini içeren özel kaynaklar.
- Kurulum API 'Leri tarafından kullanılan sürüm kaynakları.
- Menü ve iletişim kutusu kaynakları.

Projenize yeni kaynaklar ekleyebilir ve bu kaynakları uygun kaynak düzenleyicisini kullanarak değiştirebilirsiniz. Çoğu görsel C++ sihirbaz, projeniz için otomatik olarak bir. rc dosyası oluşturur.

> [!NOTE]
> **Kaynak düzenleyicileri** ve **kaynak görünümü** Express sürümlerinde kullanılamaz.

Kaynak dosyalarını yönetilen projelere el ile eklemek için bkz. [Masaüstü uygulamaları Için kaynak dosyaları oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Bu makale, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama özelliklerini içerir.

Yönetilen uygulamalardaki kaynakları globalize ve yerelleştirmek için bkz. [uygulamaları Genelleştirme ve yerelleştirme .NET Framework](/dotnet/standard/globalization-localization/index).

## <a name="in-this-section"></a>Bu Bölümde

[Kaynak Dosyalar](../windows/resource-files-visual-studio.md)<br/>
Kaynak dosyalarını ve bunların Windows masaüstü uygulamalarında nasıl kullanıldığını açıklar. Ayrıca, kaynak dosyalarının nasıl kullanılacağını betimleyen makalelere bağlantılar sağlar.

[Kaynak Tanımlayıcıları (Semboller)](../windows/symbols-resource-identifiers.md)<br/>
Sembolleri açıklar ve projelerinizde sembolleri yönetmek için **kaynak sembolleri** iletişim kutusunu kullanma hakkında bilgi sağlar.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
Visual Studio 'da sunulan kaynak düzenleyicilerini ve her düzenleyicide değiştirebileceğiniz kaynak türlerini açıklar. Ayrıca, her bir düzenleyiciyi kullanma hakkında ayrıntılı bilgi için bağlantılar sağlar.

## <a name="related-sections"></a>İlgili Bölümler

[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md)<br/>
Visual C++ belgelerine ilişkin bağlantıları sağlar.

[Bizimle İletişime Geçin](/visualstudio/ide/talk-to-us)<br/>
Belge kümesini kullanma, ürün desteğiyle iletişim kurma ve erişilebilirlik özelliklerini kullanma hakkındaki bilgilere bağlantılar sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Windows Masaüstü uygulamaları](../windows/windows-desktop-applications-cpp.md)<br/>
[Menüler ve diğer kaynaklar](/windows/win32/menurc/resources)
