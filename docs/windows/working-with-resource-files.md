---
title: Kaynak dosyaları (C++) ile çalışma
ms.date: 02/14/2019
helpviewer_keywords:
- resources [C++], about resources
- resources [C++], about resource files
- resource files [C++], about resource files
ms.assetid: 2699a539-b369-4b78-80f0-df03eb7b6780
ms.openlocfilehash: a08c7ecb153b790f06da386ac93d1f05f5981e61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387675"
---
# <a name="working-with-resource-files"></a>Kaynak Dosyalarıyla Çalışma

> [!WARNING]
> Bu bölüm, C++ ile yazılmış Windows Masaüstü uygulamaları için geçerlidir.
>
> Evrensel Windows platformu uygulamaları yazılan kaynaklar hakkında bilgi için C++, bakın [tanımlama uygulama kaynaklarını](/windows/uwp/app-resources/), veya kaynak için ekleme C++/ (yönetilen) CLI projeleri için bkz [Masaüstüuygulamalarındakikaynaklar](/dotnet/framework/resources/index) .NET Framework Geliştirici Kılavuzu'nda.

Kaynakları gibi çeşitli öğeleri oluşabilir:

- Arabirim bir bit eşlem, simgesi veya imleci gibi kullanıcı bilgilerini öğeleri.
- Veri ve uygulama içeren özel kaynaklar gerekir.
- Kurulum API'leri tarafından kullanılan sürümü kaynakları.
- Menü ve iletişim kutusu kaynakları.

Yeni kaynakları projenize ekleyin ve kaynaklarla ilgili kaynak Düzenleyicisi'ni kullanarak değiştirin. Çoğu Visual C++ sihirbazları, projeniz için bir .rc dosyasını otomatik olarak oluşturur.

> [!NOTE]
> **Kaynak düzenleyicileri** ve **kaynak görünümü** Express sürümlerinde kullanılamaz.

Kaynak dosyalarını yönetilen projelere el ile eklemek için bkz [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Bu makalede, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama işlemleri açıklanır.

Globalize ve yönetilen uygulamalardaki kaynaklar yerelleştirmek için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="in-this-section"></a>Bu Bölümde

[Kaynak Dosyalar](../windows/resource-files-visual-studio.md)<br/>
Kaynak dosyaları ve bunların Windows masaüstü uygulamalarında nasıl kullanıldığı açıklanmaktadır. Ayrıca kaynak dosyaları kullanmayı açıklayan makaleleri için bağlantılar sağlar.

[Kaynak Tanımlayıcıları (Semboller)](../windows/symbols-resource-identifiers.md)<br/>
Sembolleri tanımlar ve kullanma hakkında bilgi sağlar **kaynak sembolleri** sembolleri projelerinizde yönetmek için iletişim kutusu.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
Visual Studio ve her bir düzenleyiciyle değiştirebileceğiniz kaynak türleri için sağlanan kaynak düzenleyicileri açıklar. Ayrıca her Düzenleyicisi'ni kullanarak ayrıntılı bilgi için bağlantılar sağlar.

## <a name="related-sections"></a>İlgili Bölümler

[Visual C++](../overview/visual-cpp-in-visual-studio.md)<br/>
Visual C++ belgelerine ilişkin bağlantıları sağlar.

[Bizimle İletişime Geçin](/visualstudio/ide/talk-to-us)<br/>
Belge kümesini kullanarak, ürün desteği ile iletişime ve erişilebilirlik özelliklerini kullanan bilgilere bağlantılar sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Windows Masaüstü uygulamaları](../windows/windows-desktop-applications-cpp.md)<br/>
[Menüler ve diğer kaynaklar](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)