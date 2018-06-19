---
title: Hızlandırıcı değiştirme özelliği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d99d4656f2835f9adb60f310e429c4ccb97ac7b6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854060"
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