---
title: Proje derleme hatası PRJ0024 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
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
ms.openlocfilehash: eb539a5f1ee5f1aa5f9d828d93fa6d0dc8690c22
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215604"
---
# <a name="project-build-error-prj0024"></a>Proje Derleme Hatası PRJ0024

> Unicode yolu '*yolu*' kullanıcının ANSI kodlu sayfasına çevrilemedi.

*yol* orijinal yol dizesini Unicode sürümüdür. Bu hata durumlarda oluşabilir ANSI olarak geçerli kod sayfası için doğrudan çevrilemeyen Unicode yolu olduğu.

Bir sistemde, bilgisayarınızda değil bir kod sayfası kullanılarak geliştirilmiş bir proje ile çalışıyorsanız, bu hata oluşabilir.

Bu hata için çözüm ANSI metin kullanın veya kod sayfası bilgisayarınıza yüklemek ve sistem varsayılan olarak ayarlanmış yol güncelleştirmektir.