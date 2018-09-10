---
title: Kaynak içerikleri iletişim kutusu (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resourceincludes
dev_langs:
- C++
helpviewer_keywords:
- Resource Includes dialog box [C++]
- rc files [C++], changing storage
- symbol header files [C++], changing
- .rc files [C++], changing storage
- symbol header files [C++], read-only
- symbols [C++], symbol header files
ms.assetid: 659a54e6-e416-4045-8411-798730ff4ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ea89cdd21f4debfa23716a04630e34e3b9203c1
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313344"
---
# <a name="resource-includes-dialog-box-c"></a>Kaynak içerikleri iletişim kutusu (C++)

Kullanabileceğiniz **kaynak içerikleri** ortamının tüm kaynaklar proje .rc dosyasını ve tüm depolama olarak normal çalışma düzenleme değiştirmek için bir C++ projesi iletişim kutusunda [sembolleri](../windows/symbols-resource-identifiers.md) Resource.h içindeki.

Açmak için **kaynak içerikleri** iletişim kutusunda sağ tıklatıp bir .rc dosyasına [kaynak görünümü](../windows/resource-view-window.md), ardından **kaynak içerikleri** kısayol menüsünden.

**Sembol başlık dosyası**  
Kaynak dosyanız için Sembol tanımlarını depolandığı üst bilgi dosyasının adını değiştirmenizi sağlar. Daha fazla bilgi için [sembol üst bilgi dosyalarının adlarını değiştirme](../windows/changing-the-names-of-symbol-header-files.md).

**Salt okunur sembol yönergeleri**  
Bir düzenleme oturumu sırasında değiştirilmemelidir sembolleri içeren üstbilgi dosyalarını dahil etmenize imkan sağlar. Örneğin, çeşitli projeler arasında paylaşılan bir sembol dosyası içerebilir. MFC .h dosyaları da ekleyebilirsiniz. Daha fazla bilgi için [dahil olmak üzere paylaşılan (salt okunur) veya hesaplanan sembolleri](../windows/including-shared-read-only-or-calculated-symbols.md).

**Derleme zamanı yönergeleri**  
Oluşturulan kaynak dosyaları içerir ve ana kaynak dosyanızı kaynaklarda ayrı olarak düzenlenen derleme zamanı yönergeleri (örneğin, kaynakları koşullu olarak dahil) içeren veya özel bir biçim kaynakları içeren olanak sağlar. Ayrıca **derleme zamanı yönergeleri kutusu** standart MFC kaynak dosyalarını dahil etmek için. Daha fazla bilgi için [derleme zamanında dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md).

> [!NOTE]
> Bu metin kutularındaki girişleri görünür olarak işaretlenmiş bir .rc dosyasında `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, ve `TEXTINCLUDE 3` sırasıyla. Daha fazla bilgi için [TN035: kullanarak birden çok kaynak dosyaları ve başlık dosyaları Visual C++ ile](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).

Kullanarak, kaynak dosyaya değişiklikleri yaptıktan sonra **kaynak içerikleri** iletişim kutusunda, gereken .rc dosyasını kapatın ve değişikliklerin etkili olması yeniden açın. Daha fazla bilgi için [derleme zamanında dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Nasıl yapılır: Kaynaklar için Dizin Eklemeyi Belirtme](../windows/how-to-specify-include-directories-for-resources.md)  
[Semboller: Kaynak Tanımlayıcıları](../windows/symbols-resource-identifiers.md)  
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)  
[Kaynak Düzenleyicileri](../windows/resource-editors.md)