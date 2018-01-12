---
title: "Kaynak Derleyicisi önemli hatası RC1052 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC1052
dev_langs: C++
helpviewer_keywords: RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0546441022d8e2b487d83e291574020665cdaf4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1052"></a>Kaynak Derleyicisi Önemli Hatası RC1052
Derleyici sınırı: #if veya #ifdef blokları çok fazla iç içe  
  
 Program için en fazla izin verilen iç içe geçme düzeyi aşıldı `#if` ve `#ifdef` yönergeleri.  
  
 Bu hata oluşabilir tarafından bu önişlemci yönergeleri kullanan dosyaları içerir.  
  
 Bu sorunu düzeltin, sayısını azaltmak için iç içe `#if` ve `#ifdef` kaynak dosyanızdaki yönergeleri. Kaynak dosyanızda bulunan başlık dosyaları sorunun nedeni, sayısını, iç içe geçmiş `#if` ve `#ifdef` üstbilgi dosyaları yönergeleri. Bu mümkün değilse, oluşturma ve yeni bir üstbilgi dosyası mevcut eklenen üst bilgi dosyaları önişlemci çalıştırarak kaynak dosyanızda dahil olmak üzere göz önünde bulundurun. Daha fazla bilgi için bkz: [/P (dosyaya Önişle)](../../build/reference/p-preprocess-to-a-file.md) derleyici seçeneği.