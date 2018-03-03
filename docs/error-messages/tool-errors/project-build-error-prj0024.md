---
title: "Proje derleme hatası PRJ0024 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0024
dev_langs:
- C++
helpviewer_keywords:
- PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2cf9ad974856f132599932a32b954e50453adf56
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0024"></a>Proje Derleme Hatası PRJ0024
Unicode yolu 'path' kullanıcının ANSI kod sayfasına çevrilemedi.  
  
 ***yol*** özgün yol dizesini Unicode sürümüdür. Bu hata durumlarda oluşabilir ANSI için geçerli sistem kod sayfası için doğrudan çevrilemez bir Unicode yol olduğu.  
  
 Bu hata, bilgisayarınızda yüklü olmayan bir kod sayfası kullanılarak bir sistemde geliştirilmiştir bir proje üzerinde çalışıyorsanız oluşabilir.  
  
 Bu hata çözümü ANSI metin kullanın veya bilgisayarınızda kod sayfasını yükleyin ve sistem varsayılan olarak ayarlamak için yol güncelleştirmektir.