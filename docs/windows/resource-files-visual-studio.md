---
title: Kaynak Dosyalar (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- resources [C++]
- .rc files [C++]
- resource files [C++]
- resource script files [C++]
- resource script files [C++], Win-32 based applications
- resource script files [C++], files updated when editing resources
- resources [C++], types of resource files
- rct files [C++]
- rc files [C++]
- resource files [C++], types of
- .rct files [C++]
- resource script files [C++], unsupported types
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
ms.openlocfilehash: 9ad36f19185bc5b3430e7644ef55164d3cb0839a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461704"
---
# <a name="resource-files-c"></a>Kaynak Dosyalar (C++)

> [!NOTE]
> Bu yazıda, Windows Masaüstü uygulamaları için geçerlidir. Evrensel Windows platformu uygulamaları kaynaklar hakkında daha fazla bilgi için bkz: [tanımlama uygulama kaynaklarını](/windows/uwp/app-resources/).
>
> Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).
>
> Bu yana .NET programlama dillerinin projelerde kaynak betik dosyalarına kullanmayın kaynaklarınızdan açmalısınız **Çözüm Gezgini**. Kullanabileceğiniz [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) ve [ikili düzenleyiciyi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

"Kaynak dosyası" terimi, bir dizi gibi çeşitli dosya türleri için başvurabilir:

- Bir programın kaynak betiği (.rc) dosyası.

- Kaynak şablonu (.rct) dosyası.

- Mevcut tek başına bir dosya ayrı bir kaynak bit eşlemi, simgesi veya imleci dosyası gibi bir .rc dosyasından adlandırılır.

- Örneğin bir .rc dosyasından adlandırılır Resource.h, geliştirme ortamı tarafından oluşturulan bir üst bilgi dosyası.

Kaynakları da bulunabilir [diğer dosya türleri](../windows/editable-file-types-for-resources.md) .res .exe ve .dll dosyaları gibi. Kaynaklar ve projeniz içindeki kaynak dosyaları ve, geçerli projenin parçası olmayan dosyalarla çalışabilirsiniz. Visual Studio geliştirme ortamında oluşturulmayan kaynak dosyalarla çalışabilirsiniz. Örneğin, şunları yapabilirsiniz:

- İç içe geçmiş ve koşullu olarak dahil edilen kaynak dosyalarıyla birlikte çalışır.

- Var olan kaynakları güncelleştirme veya Visual C++ biçimine dönüştürebilirsiniz.

- Grafik kaynakları için veya geçerli kaynak dosyanızı dışarı veya içeri aktarın.

- Geliştirme ortamı tarafından değiştirilemez paylaşılan veya salt okunur tanımlayıcıları (simge) içerir.

- Geçerli projeyi, çeşitli projeler arasında paylaşılan kaynakları gibi sırasında yürütülebilir (.exe) dosya düzenleme gerektirmeyen (veya düzenlenecek istemediğiniz) kaynakları içerir.

- Geliştirme ortamı tarafından desteklenmeyen kaynak türleri içerir.

Bu bölüm kapsamaktadır:

- [Yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md)

- [Yeni kaynak oluşturma](../windows/how-to-create-a-resource.md)

- [Kaynak betik dosyası kaynakları görüntüleme](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)

- [Kaynak betik dosyasını metin biçiminde açma](../windows/how-to-open-a-resource-script-file-in-text-format.md)

- [Derleme zamanı dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md)

- [Kaynaklarını kopyalama](../windows/how-to-copy-resources.md)

- [Kaynak şablonları (.rct) kullanma](../windows/how-to-use-resource-templates.md)

- [İçeri ve dışarı aktarma kaynakları](../windows/how-to-import-and-export-resources.md)

- [Kaynaklar için Düzenlenebilir Dosya Türleri](../windows/editable-file-types-for-resources.md)

- [Kaynak Düzenlemesinden Etkilenen Dosyalar](../windows/files-affected-by-resource-editing.md)

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Menüler ve diğer kaynaklar](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)