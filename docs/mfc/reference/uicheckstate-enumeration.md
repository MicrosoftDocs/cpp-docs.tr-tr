---
title: "Uıcheckstate numaralandırması | Microsoft Docs"
ms.custom: 
ms.date: 04/03/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: afxwinforms/uicheckstate
dev_langs: C++
helpviewer_keywords: uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7feac12853066ad4971d98ce7cf25ec4d8a86fa8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="uicheckstate-enumeration"></a>UICheckState Numaralandırması
Komut için bir kullanıcı arabirimi öğesi onay durumunu açıklar.  
   
### <a name="syntax"></a>Sözdizimi   
```  
public enum class 
{  
   [DefaultValue(typeid<Microsoft::VisualC::MFC::UICheckState>, "Checked")]  
   Unchecked,   
   Checked,   
   Indeterminate 
};  
```  
   
### <a name="remarks"></a>Açıklamalar  
 [ICommandUI::Check](icommandui-interface.md#check) bir kullanıcı arabirimi öğesi durumu tanımlamak için bu değerleri kullanır.    
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll tanımlanan)  
