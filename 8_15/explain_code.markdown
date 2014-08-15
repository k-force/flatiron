

```ruby


class Movie

  MAX_DURATION = 180
 
  attr_accessor :title
  attr_accessor :rating
  attr_accessor :duration

  def initialize(title, rating, duration)
    @title = title
    @rating = rating
    @duration = duration
  end
  
  def self.too_long?(movie)
    movie.duration > MAX_DURATION
  end
  
  def play
    if Movie.too_long?(self)
      puts "Skipping #{self.title} -- too long."
    else
      puts "Playing #{self.title} (#{self.rating} stars)"
    end
  end

end

class MoviePlayer

  attr_accessor :movies

  def initialize
    @movies = []
  end

  def play
    movies.each do |movie|
      movie.play
    end
  end

end

player = MoviePlayer.new
player.movies << Movie.new("Iron Man", 5, 120)
player.movies << Movie.new("Superman", 3, 190)
player.play


```
