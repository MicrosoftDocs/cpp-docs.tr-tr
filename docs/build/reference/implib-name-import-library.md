---
description: Şu konuda daha fazla bilgi edinin:/ıMPLIB (ad Içeri aktarma kitaplığı)
title: /IMPLIB (İçeri Aktarma Kitaplığını Adlandır)
ms.date: 11/04/2016
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
ms.openlocfilehash: 2a5ea590368d1bc3abbecf38845e97a99a0d1f96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191322"
---
# <a name="implib-name-import-library"></a>/IMPLIB (İçeri Aktarma Kitaplığını Adlandır)

> /IMPLıB:*filename*

## <a name="parameters"></a>Parametreler

*filename*<br/>
İçeri aktarma kitaplığı için Kullanıcı tarafından belirtilen bir ad. Varsayılan adı değiştirir.

## <a name="remarks"></a>Açıklamalar

/IMPLıB seçeneği, dışarı aktarmalar içeren bir program oluştururken bağlantı oluşturulan içeri aktarma kitaplığının varsayılan adını geçersiz kılar. Varsayılan ad, ana çıkış dosyasının temel adından ve. lib uzantısından oluşturulur. Aşağıdakilerden biri veya birkaçı belirtilmişse, bir program dışarı aktarmalar içerir:

- Kaynak kodundaki [__declspec (dllexport)](../../cpp/dllexport-dllimport.md) anahtar sözcüğü

- Bir. def dosyasında bir ifade [dışarı aktarır](exports.md)

- BAĞLANTı komutunda bir [/Export](export-exports-a-function.md) belirtimi

İçeri aktarma kitaplığı oluşturulmadıysa bağlantı/ıMPLıB yok sayılır. Dışarı aktarma belirtilmemişse, bağlantı bir içeri aktarma kitaplığı oluşturmaz. Derlemede bir dışa aktarma dosyası kullanılıyorsa, bağlantı bir içeri aktarma kitaplığının zaten var olduğunu ve bir tane oluşturmadığından emin olur. Kitaplık ve dışarı aktarma dosyalarını içeri aktarma hakkında bilgi için bkz. [LIB Reference](lib-reference.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Gelişmiş** Özellik sayfasına tıklayın.

1. **Içeri aktarma kitaplığı** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
