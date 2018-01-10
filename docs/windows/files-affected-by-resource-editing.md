---
title: "Kaynak düzenlemesinden etkilenen dosyalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- resource editing
- resources [Visual Studio], editing
ms.assetid: d0820df1-ba84-40ac-bce9-29ea5ee7e3f8
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3b3a5f8c8351d7056409b0e6182862213c51381a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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