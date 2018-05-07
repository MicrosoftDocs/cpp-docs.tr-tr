---
title: Proje derleme hatası PRJ0024 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0024
dev_langs:
- C++
helpviewer_keywords:
- PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59bf76aba80093bf9e8e653bdfb9fad49687a501
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0024"></a>Proje Derleme Hatası PRJ0024
Unicode yolu 'path' kullanıcının ANSI kod sayfasına çevrilemedi.  
  
 ***yol*** özgün yol dizesini Unicode sürümüdür. Bu hata durumlarda oluşabilir ANSI için geçerli sistem kod sayfası için doğrudan çevrilemez bir Unicode yol olduğu.  
  
 Bu hata, bilgisayarınızda yüklü olmayan bir kod sayfası kullanılarak bir sistemde geliştirilmiştir bir proje üzerinde çalışıyorsanız oluşabilir.  
  
 Bu hata çözümü ANSI metin kullanın veya bilgisayarınızda kod sayfasını yükleyin ve sistem varsayılan olarak ayarlamak için yol güncelleştirmektir.