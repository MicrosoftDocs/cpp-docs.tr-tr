---
title: Kaynak düzenlemesinden etkilenen dosyalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource editing
- resources [Visual Studio], editing
ms.assetid: d0820df1-ba84-40ac-bce9-29ea5ee7e3f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cb103ac098c8d73db132cdb67b6ab6902ee3f591
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="files-affected-by-resource-editing"></a>Kaynak Düzenlemesinden Etkilenen Dosyalar
Visual Studio ortamında kaynak düzenleme oturumunuz sırasında aşağıdaki tabloda gösterilen dosyalar çalışır.  
  
|Dosya adı|Açıklama|  
|---------------|-----------------|  
|Kaynak.h|Geliştirme ortamı tarafından oluşturulan üstbilgi dosyası; simge tanımlarını içerir.|  
|Filename.APS|Geçerli kaynak betik dosyasını ikili sürümü; Hızlı yükleme için kullanılır.<br /><br /> Kaynak düzenleyicileri .rc veya resource.h dosyaları doğrudan okuyamadı. Kaynak Derleyicisi bunları kaynak düzenleyicileri tarafından tüketilen .aps dosyalarına derler. Bu dosyayı bir derleme adımdır ve yalnızca simgesel verileri depolar. İşlem ile normal bir derleme gibi bilgileri (örneğin, Yorumlar) sembolik değil derleme işlemi sırasında göz ardı edilir. .Aps dosya .rc dosyasıyla out eşitlenmiş alır her .rc dosyasını yeniden oluşturur (kaydettiğinizde, örneğin, Kaynak Düzenleyici .rc dosyası ve resource.h dosyası geçersiz kılar). Kaynaklardaki değişiklikleri .rc dosyasında eklenen kalır ancak .rc dosyanın üzerine sonra açıklamaları her zaman kaybolur. Açıklamaları koruma hakkında daha fazla bilgi için bkz: [derleme zamanında dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md).|  
|.rc|Komut dosyası için geçerli projenize kaynaklarında içeren kaynak komut dosyası. Bu dosya, kaydettiğiniz zaman tarafından .aps dosyanın üzerine yazılır.|  
  

  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)