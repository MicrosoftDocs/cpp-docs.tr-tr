---
title: Kaynak düzenleme (C++) tarafından etkilenen dosyalar | Microsoft Docs
ms.custom: ''
ms.date: 06/18/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource editing
- resources [C++], editing
ms.assetid: d0820df1-ba84-40ac-bce9-29ea5ee7e3f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b70a24e77e581ebab792d9fca4d7d1a3bd8db12
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316282"
---
# <a name="files-affected-by-resource-editing-c"></a>Kaynak düzenleme (C++) tarafından etkilenen dosyalar

Kaynak düzenleme oturumu sırasında aşağıdaki tabloda gösterilen dosyaları ile Visual Studio ortamında çalışır.

|Dosya adı|Açıklama|
|---------------|-----------------|
|Kaynak.h|Geliştirme ortamı tarafından oluşturulan üst bilgi dosyası Sembol tanımlarını içerir. (Bu dosya kaynak denetimine dahil).|
|Filename.APS|Geçerli kaynak betik dosyasını ikili sürümü; Hızlı yükleme için kullanılır.<br /><br /> Kaynak düzenleyicileri .rc veya resource.h dosyaları doğrudan okunmaz. Kaynak Derleyicisi bunları kaynak düzenleyicileri tarafından tüketilen .aps dosyalarına derlenir. Bu dosya, bir derleme adımdır ve yalnızca sembolik verileri depolar. (Örneğin, açıklamalar) sembolik değil bilgi işlem ile normal bir derleme olarak derleme işlemi sırasında göz ardı edilir. .Rc dosyasıyla .aps dosyası zaman uyumsuz olarak alır her .rc dosyası yeniden oluşturuldu (kaydettiğinizde, örneğin, kaynak düzenleyicisini .rc dosyasını ve resource.h dosyasını geçersiz kılar). Herhangi bir değişiklik kaynaklardaki .rc dosyasına eklenen kalır ancak .rc dosyasının üzerine sonra açıklamalar her zaman kaybolacak. Açıklamaları koruma hakkında daha fazla bilgi için bkz: [derleme zamanında dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md). (Genellikle, .aps dosya kaynak denetimine eklememelisiniz.)|
|.rc|Komut dosyası için geçerli projenizdeki kaynakları içeren kaynak komut dosyası. Bu dosya, kaydettiğiniz her .aps dosyası tarafından üzerine yazılır. (Bu dosya kaynak denetimine dahil).|

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)