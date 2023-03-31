# Vezir Problemi

Tabu arama algoritması, karmaşık optimizasyon problemlerini çözmek için kullanılan bir meta-sezgisel algoritmadır. Tabu arama, diğer sezgisel algoritmalar gibi genetik algoritma veya simüle edilmiş tavlama gibi tekniklerden farklı olarak, sadece mevcut çözüm değerlerini değil, aynı zamanda geçmiş çözümler arasındaki geçişleri de dikkate alır.

Bu algoritma, adımlarını Tabu Listesi olarak adlandırılan bir dizi engelleme kuralı ile belirler. Tabu Listesi, mevcut çözümü değiştirmeye yönelik kısıtlamalar getirerek, daha önce denenmiş fakat daha kötü çözümlere geri dönüşü engeller. Bu sayede, arama alanında daha etkili bir keşif yaparak optimum çözüme daha hızlı ulaşabilir.

Bu dokümanda, bir vezir problemi örneği üzerinde, genetik algoritma ile tabu arama algoritmasının nasıl kullanılabileceğine dair bir örnek sunulacaktır. Aşağıdaki adımlar takip edilecektir:
![WhatsApp Görsel 2023-03-29 saat 22 14 09](https://user-images.githubusercontent.com/96746943/229240834-87368b77-df9a-45d8-a388-ee673c122a55.jpg)

1. Problemin tanımı ve kısıtları:
    - Bir 8x8 satranç tahtası üzerinde, 8 vezirin yerleştirilmesi gerekmektedir.
    - Her vezir, aynı satır, sütun veya diyagonalde başka bir vezir olmamalıdır.
    - Amaç, tüm vezirlerin birbirini tehdit etmediği, yani tüm kısıtları sağlayan bir yerleşim bulmaktır.
    - Bir vezir icin ceza, tehdit ettigi vezir sayisidir.
    - Populasyon buyuklugu: 10
    - Caprazlama Orani : %60 (Permutasyon)
    - Mutasyoin Orani: %1 (Insert veya Swap )
    - Strateji: Populasyondaki en kotuyu yer degistirir
    - Iterasyon Sayisi: 10
2. Genetik algoritma kullanarak vezir problemi çözümü:
    - Başlangıçta, popülasyon, rasgele 8 vezir yerleşimi içerecek şekilde oluşturulur.
    - Fitness fonksiyonu, her bir vezirin tehdit ettiği diğer vezir sayısını hesaplar ve toplam tehdit sayısını döndürür. Cezalandırma fonksiyonu, tehdit sayısının tersi olarak hesaplanır. Yani, daha az tehdit edilen vezirler daha yüksek puan alır.
    - Seçim işlemi, fitness değerine göre turnuva seçimi kullanarak yapılır. Popülasyonun en iyi çözümleri seçilir ve ebeveyn olarak atanır.
    - Çaprazlama işlemi, bir ebeveyn çiftinin rastgele seçilen noktalarından bölünür ve çocuklar oluşturulur. Bu örnekte, permütasyon çaprazlama yöntemi kullanılır.
    - Mutasyon işlemi, popülasyonun belirli bir yüzdesinde, rastgele bir yerde veya iki vezirin yerini değiştirerek yapılır.
    - Yeni popülasyon, ebeveynler ve çocuklar arasından seçilerek oluşturulur. Seçim işlemi, fitness değerine göre turnuva seçimi kullanarak yapılır.
    - Popülasyon, belirli bir iterasyon sayısı veya belirli bir süre boyunca değişmediğinde durur.
    1. Tabu arama kullanarak vezir problemi çözümü:
        - Başlangıçta, popülasyon, rasgele 8 vezir yerleşimi içerecek şekilde oluşturulur.
        - Fitness fonksiyonu, her bir vezirin tehdit ettiği diğer vezir sayısını hesaplar ve toplam tehdit sayısını döndürür. Cezalandırma fonksiyonu, tehdit sayısının tersi olarak hesaplanır. Yani, daha az tehdit edilen vezirler daha yüksek puan alır.
        - Başlangıçta, en iyi çözüm ve çözüme ait fitness değeri kaydedilir.
        - Tabu Listesi, mevcut çözümü değiştirmeye yönelik kısıtlamalar getirerek, daha önce denenmiş fakat daha kötü çözümlere geri dönüşü engeller. Bu sayede, arama alanında daha etkili bir keşif yaparak optimum çözüme daha hızlı ulaşılabilir.
        - Her iterasyonda, en iyi çözüm ve çözüme ait fitness değeri kaydedilir.
        - Yeni çözümler oluşturulur ve fitness değerleri hesaplanır.
        - Tabu Listesi kullanılarak, mevcut çözüme dönüş yapmamak koşulu ile en iyi yeni çözüm seçilir.
        - Popülasyonun belirli bir yüzdesi, rasgele mutasyona uğrar.
        - Popülasyonun belirli bir yüzdesi, en kötü çözümleri yer değiştirmek için seçilir ve yer değiştirme işlemi yapılır.
        - Popülasyon, belirli bir iterasyon sayısı veya belirli bir süre boyunca değişmediğinde durur.
    2. Karşılaştırma ve sonuçlar:
        - Her iki algoritmanın da amacı, vezir problemi için optimum çözümü bulmaktır.
        - Genetik algoritma, daha az hesaplama süresi gerektiren bir algoritma olarak bilinir ve daha küçük problemler için daha etkilidir.
        - Tabu arama, daha büyük problemlerde daha etkilidir ve daha iyi sonuçlar verir, ancak daha uzun hesaplama süresi gerektirir.
        - Sonuç olarak, vezir problemi gibi küçük problemler için genetik algoritma, daha büyük problemler için ise tabu arama daha uygun bir seçenek olabilir.
    
    Bu doküman, bir vezir problemi örneği üzerinden genetik algoritma ve tabu arama algoritmalarının nasıl çalıştığını ve birbirlerinden nasıl farklılaştığını açıklamaktadır. Ayrıca her iki algoritmanın vezir problemi için nasıl uygulanacağına dair bir örnek de sunulmuştur.
    
    İki algoritma arasındaki en temel fark, genetik algoritmanın evrim teorisine dayalı olması, tabu aramanın ise bir meta-sezgisel optimizasyon yöntemi olmasıdır. Genetik algoritma, bir populasyon içindeki bireylerin genetik materyallerini çaprazlamayla birleştirerek yeni nesiller oluşturur. Tabu arama ise, mevcut çözümlere kısıtlamalar getirerek daha iyi sonuçlar elde etmeye çalışır.
    
    Genetik algoritmanın bir dezavantajı, en iyi çözüme yakınsamak için daha fazla sayıda iterasyona ihtiyaç duymasıdır. Tabu arama ise, daha büyük problemlerde daha etkilidir ve daha iyi sonuçlar verir, ancak daha uzun hesaplama süresi gerektirir.
    
    Sonuç olarak, vezir problemi gibi küçük problemler için genetik algoritma, daha büyük problemler için ise tabu arama daha uygun bir seçenek olabilir. Her iki algoritma da avantaj ve dezavantajlarına sahip olmakla birlikte, uygulanacak problemin boyutu ve doğası, hangi algoritmanın tercih edileceğini belirleyecektir.
    
    Aşağıda yazdığım C# kodu  verilen 8x8 şah tahtası üzerinde bir vezir problemi için GA algoritması uygulamakta.
    
    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Linq;
    
    class Program
    {
        static int[] fitness(List<int[]> population)
        {
            int[] fitness = new int[population.Count];
            for (int i = 0; i < population.Count; i++)
            {
                int penalty = 0;
                for (int j = 0; j < population[i].Length; j++)
                {
                    for (int k = j + 1; k < population[i].Length; k++)
                    {
                        if (population[i][j] == population[i][k])
                        {
                            penalty++;
                        }
                        else if (Math.Abs(population[i][j] - population[i][k]) == Math.Abs(j - k))
                        {
                            penalty++;
                        }
                    }
                }
                fitness[i] = 28 - penalty;
            }
            return fitness;
        }
    
        static int[] selection(int[] fitness, int num_parents)
        {
            int[] parents = new int[num_parents];
            for (int i = 0; i < num_parents; i++)
            {
                int max_fitness_idx = Array.IndexOf(fitness, fitness.Max());
                parents[i] = max_fitness_idx;
                fitness[max_fitness_idx] = -1;
            }
            return parents;
        }
    
        static List<int[]> crossover(List<int[]> parents, int offspring_size)
        {
            List<int[]> offspring = new List<int[]>();
            Random rand = new Random();
            for (int i = 0; i < offspring_size; i++)
            {
                int[] parent1 = parents[rand.Next(parents.Count)];
                int[] parent2 = parents[rand.Next(parents.Count)];
                int[] child = new int[parent1.Length];
                int crossover_point = rand.Next(1, parent1.Length);
                Array.Copy(parent1, child, crossover_point);
                Array.Copy(parent2, crossover_point, child, crossover_point, parent2.Length - crossover_point);
                offspring.Add(child);
            }
            return offspring;
        }
    
        static List<int[]> mutation(List<int[]> offspring, double mutation_rate)
        {
            Random rand = new Random();
            for (int i = 0; i < offspring.Count; i++)
            {
                if (rand.NextDouble() < mutation_rate)
                {
                    int gene_idx1 = rand.Next(offspring[i].Length);
                    int gene_idx2 = rand.Next(offspring[i].Length);
                    int temp = offspring[i][gene_idx1];
                    offspring[i][gene_idx1] = offspring[i][gene_idx2];
                    offspring[i][gene_idx2] = temp;
                }
            }
            return offspring;
        }
    
        static int[] best_solution(List<int[]> population, int[] fitness)
        {
            int max_fitness_idx = Array.IndexOf(fitness, fitness.Max());
            return population[max_fitness_idx];
        }
    
        static void Main(string[] args)
        {
            int population_size = 10;
            double crossover_rate = 0.6;
            double mutation_rate = 0.01;
            int iterations = 10;
    
            // Initial population
            List<int[]> population = new List<int[]>();
            Random rand = new Random();
            for (int i = 0; i < population_size; i++)
            {
                int[] individual = Enumerable.Range(1, 8).OrderBy(x => rand.Next()).ToArray();
                population.Add(individual);
            }
    
            for (int iter = 0; iter < iterations; iter++)
            {
                int[] fitness_values =fitness(population);
            // Select parents
            int num_parents = (int)(population_size * crossover_rate);
            int[] parents_idx = selection(fitness_values, num_parents);
            List<int[]> parents = new List<int[]>();
            foreach (int idx in parents_idx)
            {
                parents.Add(population[idx]);
            }
    
            // Crossover
            int offspring_size = population_size - num_parents;
            List<int[]> offspring = crossover(parents, offspring_size);
    
            // Mutation
            offspring = mutation(offspring, mutation_rate);
    
            // New population
            population.Clear();
            population.AddRange(parents);
            population.AddRange(offspring);
    
            // Best solution
            int[] best_sol = best_solution(population, fitness_values);
            Console.WriteLine("Iteration {0}: Best solution = [{1}]", iter + 1, string.Join(", ", best_sol));
        }
    }
    }
    ```

    ![20230401_005702](https://user-images.githubusercontent.com/96746943/229240878-42810cd8-323f-4f04-831b-3367a2566b9b.gif)

    
    Bu program, genetik algoritma kullanarak 8-vezir problemini çözer. Program, rastgele başlayan bir popülasyon yaratır ve popülasyondaki her bir bireyin uygunluğunu hesaplar. Uygunluğu hesaplamak, her bir vezirin diğer vezirlerle çakışıp çakışmadığını kontrol etmek için yapılır. Daha sonra, seçilim, çaprazlama ve mutasyon işlemleri uygulanır. Bu işlemlerin ardından, yeni bir popülasyon oluşturulur ve işlem birkaç kez tekrarlanır. Sonuçta, en uygun bireyin değeri çıktı olarak verilir.
    
    Kodda her bir adım aşağıda açıklanmıştır:
    
    - fitness(population) fonksiyonu
    - Popülasyon içindeki her bir bireyin uygunluğunu hesaplar ve uygunluk değerlerini bir dizi olarak döndürür.
    - Uygunluk, her bir vezirin diğer vezirlerle çakışıp çakışmadığını kontrol etmek için hesaplanır. Her bir çift vezir arasındaki yatay, dikey ve çapraz farkları kontrol edilir. Herhangi bir çakışma varsa, uygunluk değeri azaltılır.
    - selection(fitness, num_parents) fonksiyonu
    - Fitness değerleri ile birlikte popülasyondan num_parents sayıda en iyi bireyleri seçer.
    - En iyi bireyler, fitness değerlerine göre seçilir.
    - crossover(parents, offspring_size) fonksiyonu
    - Belirtilen sayıda yeni bireyler üretir.
    - Üretim için rastgele seçilen iki ebeveyn arasında crossover yapılır. Crossover noktası rastgele belirlenir ve yeni birey, her bir ebeveynin genlerinin bir kısmını alır.
    - mutation(offspring, mutation_rate) fonksiyonu
    - Yeni bireylerin bazı genlerinde değişiklik yapar.
    - Her bir bireyin her bir geninde, belirtilen mutasyon oranına göre değişiklik yapılır. Bu, rastgele seçilen iki genin yerlerinin değiştirilmesiyle yapılır.
    - best_solution(population, fitness) fonksiyonu
    - Popülasyondaki en iyi bireyin değerini döndürür.
    - Main fonksiyonu
    - Programın ana işlevi.
    - İlk olarak, popülasyon boyutu, çaprazlama oranı, mutasyon oranı ve iterasyon sayısı gibi parametreler ayarlanır.
    - Ardından, rastgele bir popülasyon yaratılır ve belirtilen sayıda iterasyon yapılır.
    - Her bir iterasyonda, fitness değerleri hesaplanır ve ebeveynler seçilir.
    1. Crossover adımı: crossover metodunu çağırarak, seçilen ebeveynlerden yeni çocuklar oluşturuyoruz. Offspring listesine eklenen yeni çocukları tutuyoruz.
    2. Mutasyon adımı: mutation metodunu çağırarak, offspring listesindeki bireylerin genlerinde mutasyon yapıyoruz.
    3. Yeni populasyon oluşturma adımı: population listesini temizleyerek, ebeveynleri ve çocukları ekliyoruz.
    4. En iyi çözüm adımı: best_solution metodunu çağırarak, yeni populasyon için en iyi çözümü buluyoruz.
    5. Son olarak, Console.WriteLine() yöntemini kullanarak her iterasyonda en iyi çözümü yazdırıyoruz.
    
    İterasyonlar devam ederken, her iterasyonda en iyi çözüm geliştirilir ve ekrana yazdırılır. Bu şekilde, tüm iterasyonlar tamamlandığında, en iyi çözüm bulunur.

