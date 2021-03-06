# GEO-SQL

* [Описание на русском](README_RU.md)
* [Опис українською](README_UA.md)

## MYSQL Structure

```
SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET AUTOCOMMIT = 0;
START TRANSACTION;
SET time_zone = "+00:00";

CREATE TABLE `jugeo_cities` (
  `id` int(11) NOT NULL,
  `country` char(2) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `region` varchar(22) COLLATE utf8mb4_unicode_ci NOT NULL,
  `capital` int(11) NOT NULL,
  `major` int(11) NOT NULL,
  `city_en` varchar(49) COLLATE utf8mb4_unicode_ci NOT NULL,
  `city_ru` varchar(49) COLLATE utf8mb4_unicode_ci NOT NULL,
  `city_uk` varchar(49) COLLATE utf8mb4_unicode_ci NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

CREATE TABLE `jugeo_countries` (
  `id` int(11) NOT NULL,
  `order` int(11) NOT NULL,
  `code` varchar(2) COLLATE utf8mb4_unicode_ci NOT NULL,
  `name_en` varchar(144) COLLATE utf8mb4_unicode_ci NOT NULL,
  `name_ru` varchar(144) COLLATE utf8mb4_unicode_ci NOT NULL,
  `name_uk` varchar(144) COLLATE utf8mb4_unicode_ci NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

CREATE TABLE `jugeo_regions` (
  `id` int(11) NOT NULL,
  `country` varchar(2) COLLATE utf8mb4_unicode_ci NOT NULL,
  `region` varchar(22) COLLATE utf8mb4_unicode_ci NOT NULL,
  `region_en` varchar(144) COLLATE utf8mb4_unicode_ci NOT NULL,
  `region_ru` varchar(144) COLLATE utf8mb4_unicode_ci NOT NULL,
  `region_uk` varchar(144) COLLATE utf8mb4_unicode_ci NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;


ALTER TABLE `jugeo_cities`
  ADD PRIMARY KEY (`id`),
  ADD KEY `idx` (`id`) USING BTREE,
  ADD KEY `country` (`country`),
  ADD KEY `region` (`region`),
  ADD KEY `capital` (`capital`),
  ADD KEY `major` (`major`),
  ADD KEY `city_en` (`city_en`),
  ADD KEY `city_ru` (`city_ru`),
  ADD KEY `city_uk` (`city_uk`);

ALTER TABLE `jugeo_countries`
  ADD PRIMARY KEY (`id`),
  ADD KEY `idx` (`id`) USING BTREE,
  ADD KEY `order` (`order`),
  ADD KEY `code` (`code`),
  ADD KEY `name_en` (`name_en`),
  ADD KEY `name_ru` (`name_ru`),
  ADD KEY `name_uk` (`name_uk`);

ALTER TABLE `jugeo_regions`
  ADD PRIMARY KEY (`id`),
  ADD KEY `idx` (`id`) USING BTREE,
  ADD KEY `country` (`country`),
  ADD KEY `region` (`region`),
  ADD KEY `region_en` (`region_en`),
  ADD KEY `region_ru` (`region_ru`),
  ADD KEY `region_uk` (`region_uk`);


ALTER TABLE `jugeo_cities`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=54915;
ALTER TABLE `jugeo_countries`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=247;
ALTER TABLE `jugeo_regions`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=4109;COMMIT;
```
