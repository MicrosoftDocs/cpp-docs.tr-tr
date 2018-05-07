---
title: Kaynak Derleyicisi önemli hatası RC1052 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1052
dev_langs:
- C++
helpviewer_keywords:
- RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e0651f8c2b48ea69e7137ffa3415ddaffd8fe44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-fatal-error-rc1052"></a>Kaynak Derleyicisi Önemli Hatası RC1052
Derleyici sınırı: #if veya #ifdef blokları çok fazla iç içe  
  
 Program için en fazla izin verilen iç içe geçme düzeyi aşıldı `#if` ve `#ifdef` yönergeleri.  
  
 Bu hata oluşabilir tarafından bu önişlemci yönergeleri kullanan dosyaları içerir.  
  
 Bu sorunu düzeltin, sayısını azaltmak için iç içe `#if` ve `#ifdef` kaynak dosyanızdaki yönergeleri. Kaynak dosyanızda bulunan başlık dosyaları sorunun nedeni, sayısını, iç içe geçmiş `#if` ve `#ifdef` üstbilgi dosyaları yönergeleri. Bu mümkün değilse, oluşturma ve yeni bir üstbilgi dosyası mevcut eklenen üst bilgi dosyaları önişlemci çalıştırarak kaynak dosyanızda dahil olmak üzere göz önünde bulundurun. Daha fazla bilgi için bkz: [/P (dosyaya Önişle)](../../build/reference/p-preprocess-to-a-file.md) derleyici seçeneği.