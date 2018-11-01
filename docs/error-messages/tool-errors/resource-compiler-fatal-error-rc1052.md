---
title: Kaynak Derleyicisi Önemli Hatası RC1052
ms.date: 11/04/2016
f1_keywords:
- RC1052
helpviewer_keywords:
- RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
ms.openlocfilehash: 2ab9dd48420ca263abbf3da22da878a3e74a2151
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488419"
---
# <a name="resource-compiler-fatal-error-rc1052"></a>Kaynak Derleyicisi Önemli Hatası RC1052

Derleyici sınırı: #if veya #ifdef bloklar çok derin iç içe

Program için en fazla izin verilen iç içe geçme düzeyi aşıldı `#if` ve `#ifdef` yönergeleri.

Bu hataya neden bu ön işlemci yönergeleri kullanan dosyalar arasında vardır.

Bu sorunu gidermek için sayısını azaltmak için iç içe geçmiş `#if` ve `#ifdef` kaynak dosyanızdaki yönergeleri. Sorun, kaynak dosyasında bulunan üst bilgi dosyaları tarafından neden oluyorsa, sayısını azaltın. iç içe geçmiş `#if` ve `#ifdef` üstbilgi dosyalarında yönergeleri. Bu mümkün değilse, oluşturmak ve yeni bir üstbilgi dosyası mevcut dahil edilen üst bilgi dosyaları önişlemci çalıştırarak kaynak dosyanızı dahil olmak üzere göz önünde bulundurun. Daha fazla bilgi için [/P (dosyaya ön işleme)](../../build/reference/p-preprocess-to-a-file.md) derleyici seçeneği.