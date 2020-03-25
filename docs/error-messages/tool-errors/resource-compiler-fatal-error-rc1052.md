---
title: Kaynak Derleyicisi Önemli Hatası RC1052
ms.date: 11/04/2016
f1_keywords:
- RC1052
helpviewer_keywords:
- RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
ms.openlocfilehash: ad0fe23b20870610c5979d6ad85fce55b4e506d3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182562"
---
# <a name="resource-compiler-fatal-error-rc1052"></a>Kaynak Derleyicisi Önemli Hatası RC1052

Derleyici sınırı: çok derin iç içe #if veya #ifdef blokları

Program, `#if` ve `#ifdef` yönergeleri için izin verilen en yüksek iç içe geçme düzeylerini aştı.

Bu hata, bu önişlemci yönergelerini kullanan içerme dosyalarından kaynaklanıyor olabilir.

Bu sorunu onarmak için, kaynak dosyanızdaki iç içe `#if` ve `#ifdef` yönergelerinin sayısını azaltın. Sorun, kaynak dosyanıza dahil olan üstbilgi dosyalarından kaynaklanıyorsa, üst bilgi dosyalarındaki iç içe `#if` ve `#ifdef` yönergelerinin sayısını azaltın. Bu mümkün değilse, mevcut eklenen üst bilgi dosyalarında Önişlemci 'yi çalıştırarak kaynak dosyanızda yeni bir üst bilgi dosyası oluşturmayı ve eklemeyi düşünün. Daha fazla bilgi için bkz. [/p (bir dosyaya ön işleme)](../../build/reference/p-preprocess-to-a-file.md) derleyici seçeneği.
