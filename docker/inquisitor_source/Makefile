# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: xxxxxxx <xxxxxxx@student.42.fr>            +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2023/09/14 13:51:18 by xxxxxxx           #+#    #+#              #
#    Updated: 2023/09/14 13:51:20 by xxxxxxx          ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME = inquisitor

SRCS_FILE = arping main capture_and_forward
SRCS = $(addprefix srcs/, $(addsuffix .cpp, $(SRCS_FILE)))

INCS_FILE = arping main capture_and_forward
INCS = $(addprefix incs/, $(addsuffix .hpp, $(INCS_FILE)))

OBJS = $(SRCS:.cpp=.o)

CC = c++
CFLAGS = -pthread -lpcap

all: $(NAME)

$(NAME): $(OBJS) $(INCS)
	$(CC) $(CFLAGS) $(OBJS) -o $(NAME)

.cpp.o:
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -f $(OBJS)

fclean: clean
	rm -f $(NAME)

re: fclean all

.PHONY : all clean fclean re