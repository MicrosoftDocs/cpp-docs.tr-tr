---
title: "Hızlandırıcı değiştirme özelliği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 63d6a4b526fc1f2aeb2a942e682a8c7cc6f9b58c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="accelerator-modifier-property"></a>Hızlandırıcı Değiştirme Özelliği
Hızlandırıcı tablosunda değiştirici özelliği için yasal girdileri verilmiştir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|**Yok**|Kullanıcı yalnızca anahtar değer basar. Bu en verimli şekilde 026 aracılığıyla 001 ASCII/ANSI değerlerle olarak yorumlanan kullanılır ^ A-^ Z (CTRL-CTRL-Z A).|  
|**Alt**|Kullanıcı anahtar değer önce ALT tuşuna basmanız gerekir.|  
|**CTRL**|Kullanıcı anahtar değer önce CTRL tuşuna basmanız gerekir. ASCII türü geçerli değil.|  
|**Kaydırma**|Kullanıcı anahtar değer önce SHIFT tuşuna basmanız gerekir.|  
|**Ctrl + Alt**|Kullanıcı CTRL tuşunu ve anahtar değer önce ALT tuşuna basmanız gerekir. ASCII türü geçerli değil.|  
|**Ctrl + Shift**|Kullanıcı CTRL tuşunu ve anahtar değer önce SHIFT tuşuna basmanız gerekir. ASCII türü geçerli değil.|  
|**Alt + üst karakter**|Kullanıcı ALT anahtarını ve anahtar değer önce SHIFT tuşuna basmanız gerekir. ASCII türü geçerli değil.|  
|**Ctrl + Alt + üst karakter**|Kullanıcı CTRL, ALT ve üst karakter önce anahtar değer basmalısınız. ASCII türü geçerli değil.|  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı özelliklerini ayarlama](../windows/setting-accelerator-properties.md)   
 [Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)