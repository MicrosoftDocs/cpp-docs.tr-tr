---
title: Kaynaklar (C++) için düzenlenebilir dosya türleri
ms.date: 11/04/2016
f1_keywords:
- vc.editors.resource
helpviewer_keywords:
- file types [C++], for resources
- resources [C++], editing
- files [C++], editable types
- resource editing
ms.assetid: c40f9204-f2f2-400b-9f53-53b7bf291356
ms.openlocfilehash: 9f688c144a3453c2de849b36f34f6a465e3dfeae
ms.sourcegitcommit: 5a7dbd640376e13379f5d5b2cf66c4842e5e737b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55905725"
---
# <a name="editable-file-types-for-resources-c"></a>Kaynaklar (C++) için düzenlenebilir dosya türleri

Aşağıdaki dosya türlerini açın ve içerdikleri kaynaklara düzenleyin.

|Dosya adı|Açıklama|
|---------------|-----------------|
|.rc|Kaynak betik dosyalarına.|
|.rct|Kaynak şablon dosyaları.|
|.res|Kaynak dosyaları.|
|.resx|Yönetilen kaynak dosyaları.|
|.exe|Yürütülebilir dosyalar.|
|.dll|Dinamik bağlantı kitaplığı dosyaları.|
|.bmp, .ico, .dib ve .cur|Bit eşlem ve simge, araç ve imleç dosyaları.|

## <a name="files-affected-by-resource-editing"></a>Kaynak düzenlemesinden etkilenen dosyalar

Kaynak düzenleme oturumu sırasında aşağıdaki tabloda gösterilen dosyaları ile Visual Studio ortamında çalışır.

|Dosya adı|Açıklama|
|---------------|-----------------|
|Kaynak.h|Geliştirme ortamı tarafından oluşturulan üst bilgi dosyası Sembol tanımlarını içerir. (Bu dosya kaynak denetimine dahil).|
|Filename.APS|Geçerli kaynak betik dosyasını ikili sürümü; Hızlı yükleme için kullanılır.<br /><br /> Kaynak düzenleyicileri .rc veya resource.h dosyaları doğrudan okunmaz. Kaynak Derleyicisi bunları kaynak düzenleyicileri tarafından tüketilen .aps dosyalarına derlenir. Bu dosya, bir derleme adımdır ve yalnızca sembolik verileri depolar. (Örneğin, açıklamalar) sembolik değil bilgi işlem ile normal bir derleme olarak derleme işlemi sırasında göz ardı edilir. .Rc dosyasıyla .aps dosyası zaman uyumsuz olarak alır her .rc dosyası yeniden oluşturuldu (kaydettiğinizde, örneğin, kaynak düzenleyicisini .rc dosyasını ve resource.h dosyasını geçersiz kılar). Herhangi bir değişiklik kaynaklardaki .rc dosyasına eklenen kalır ancak .rc dosyasının üzerine sonra açıklamalar her zaman kaybolacak. Açıklamaları koruma hakkında daha fazla bilgi için bkz: [derleme zamanında dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md). (Genellikle, .aps dosya kaynak denetimine eklememelisiniz.)|
|.rc|Komut dosyası için geçerli projenizdeki kaynakları içeren kaynak komut dosyası. Bu dosya, kaydettiğiniz her .aps dosyası tarafından üzerine yazılır. (Bu dosya kaynak denetimine dahil).|

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)