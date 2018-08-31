---
title: Kaynak dosyaları (Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio]
- .rc files
- resource files
- resource script files
- resource script files, Win-32 based applications
- resource script files, files updated when editing resources
- resources [Visual Studio], types of resource files
- rct files
- resources [C++]
- rc files
- resource files, types of
- .rct files
- resource script files, unsupported types
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99cf5f3c1eb0a81a636407a722149d6cee1bee64
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220692"
---
# <a name="resource-files-visual-studio"></a>Kaynak Dosyalar (Visual Studio)

> [!NOTE]
> Bu yazıda, Windows Masaüstü uygulamaları için geçerlidir. Evrensel Windows platformu uygulamaları kaynaklar hakkında daha fazla bilgi için bkz: [tanımlama uygulama kaynaklarını](https://msdn.microsoft.com/476ea844-632c-4467-9ce3-966be1350dd4).
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

[Kaynak Düzenleyicileri](../windows/resource-editors.md)  
[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)  
[Menüler ve diğer kaynaklar](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)