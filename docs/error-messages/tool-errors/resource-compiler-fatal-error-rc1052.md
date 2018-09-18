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
ms.openlocfilehash: ef276bdecf675a178f43f22e3aef88f4ed1c73cd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071191"
---
# <a name="resource-compiler-fatal-error-rc1052"></a>Kaynak Derleyicisi Önemli Hatası RC1052

Derleyici sınırı: #if veya #ifdef bloklar çok derin iç içe

Program için en fazla izin verilen iç içe geçme düzeyi aşıldı `#if` ve `#ifdef` yönergeleri.

Bu hataya neden bu ön işlemci yönergeleri kullanan dosyalar arasında vardır.

Bu sorunu gidermek için sayısını azaltmak için iç içe geçmiş `#if` ve `#ifdef` kaynak dosyanızdaki yönergeleri. Sorun, kaynak dosyasında bulunan üst bilgi dosyaları tarafından neden oluyorsa, sayısını azaltın. iç içe geçmiş `#if` ve `#ifdef` üstbilgi dosyalarında yönergeleri. Bu mümkün değilse, oluşturmak ve yeni bir üstbilgi dosyası mevcut dahil edilen üst bilgi dosyaları önişlemci çalıştırarak kaynak dosyanızı dahil olmak üzere göz önünde bulundurun. Daha fazla bilgi için [/P (dosyaya ön işleme)](../../build/reference/p-preprocess-to-a-file.md) derleyici seçeneği.